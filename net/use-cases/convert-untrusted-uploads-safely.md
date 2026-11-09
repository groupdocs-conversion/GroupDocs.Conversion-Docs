---
id: convert-untrusted-uploads-safely
url: conversion/net/use-cases/convert-untrusted-uploads-safely
title: Convert untrusted HTML and SVG uploads safely
weight: 1
description: "Compare five ways to convert untrusted HTML and SVG uploads to PDF with GroupDocs.Conversion for .NET, and which one keeps a stranger's file out of your output."
keywords: GroupDocs.Conversion, .NET, SSRF, untrusted uploads, file upload security, external resources, IExternalResourceHandler, WhitelistedResources, HTML to PDF, SVG to PDF
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

{{< alert style="info" >}}
💡 Full working example available on GitHub:
[secure-untrusted-document-upload-conversion-dotnet](https://github.com/groupdocs-conversion/secure-untrusted-document-upload-conversion-dotnet)
{{< /alert >}}

## Introduction

Convert an uploaded invoice from its saved path, and a second company's
signature turns up inside the PDF - a file that was never part of the
invoice, pulled in from the same folder on disk. Nothing was fetched over
a network to cause that leak. Choosing how to load an upload is a
GroupDocs.Conversion capability for .NET that decides whether one
stranger's file can reach another stranger's output.

This guide compares five ways the same invoice and drawing behave under
GroupDocs.Conversion for .NET 26.10.

## What This Guide Covers

Five short methods convert the same two untrusted files - an HTML invoice
and an SVG drawing - changing only the input source, the load options
class, or the whitelist entry. By the end you'll know which combination
blocks a same-folder leak, which lets a reviewed logo through without a
network request, and which whitelist syntax fails loudly instead of
matching too much.

**Prerequisites:**
- .NET SDK 8.0 or later.
- GroupDocs.Conversion for .NET 26.10.0, installed via NuGet (a
  [temporary license](https://purchase.groupdocs.com/temp-license/100032)
  removes evaluation limits).

```bash
dotnet add package GroupDocs.Conversion --version 26.10.0
```

## Which method should I start from?

Start from `ConvertUploadFromStream`, not `ConvertUploadFromPath`. Loading
an upload from a stream removes the one thing that makes conversion
dangerous for a shared uploads folder: a base folder for relative
references to resolve against. Add `ConvertWithTrustedAsset`'s dictionary
only for the specific assets - a logo, a letterhead - you've actually
reviewed and want to keep.

## Quick Decision Matrix

| Scenario | Recommended Method | Why |
|---|---|---|
| A fresh upload, just saved | `ConvertUploadFromStream` | No base folder - nothing nearby can leak in |
| Need to keep a reviewed logo or letterhead | `ConvertWithTrustedAsset` | Supplies known bytes; nothing is fetched |
| The upload is SVG, not HTML | `ConvertSvgUpload` | Same handler contract, through `SvgLoadOptions` |
| Writing a `WhitelistedResources` entry | `RejectLooseWhitelistEntry` | Shows the exact prefix rule before you ship one |
| Converting straight from a saved path | `ConvertUploadFromPath` | Only safe when the folder holds nothing else |

## Repository Structure

```
secure-untrusted-document-upload-conversion-dotnet/
├── Program.cs
├── UntrustedUploadsDemo.csproj
└── resources/
    ├── brand/logo.svg
    └── uploads/
        ├── drawing-upload.svg
        ├── invoice-upload.html
        └── other-customer-signature.svg
```

`Program.cs` holds all five methods below plus `ResourceAudit`, the
`IExternalResourceHandler` the first four pass to their load options to
record each decision. The snippets below use `ResourceAudit` without
repeating it; see
[its code in `Program.cs`](https://github.com/groupdocs-conversion/secure-untrusted-document-upload-conversion-dotnet/blob/main/Program.cs#L234-L269).

## Method 1: ConvertUploadFromPath

**Overview:** Converts the invoice from the path it was saved to, with no
extra configuration beyond the handler.

#### How It Works

`Converter` takes the upload's own path, so the folder it sits in counts
as part of the document. Remote URLs, UNC paths, and files outside that
folder are still denied by `SkipExternalResources`. Anything already
inside the folder is not "outside" anything, so it loads.

#### When to Use

- ✅ The upload has a dedicated, single-tenant folder of its own
- ✅ You need the file path for other processing steps anyway
- ❌ Not recommended for: a shared or multi-tenant uploads folder

#### Implementation

```csharp
var audit = new ResourceAudit();
var loadOptions = new WebLoadOptions { ExternalResourceHandler = audit };

using (var converter = new Converter(uploadPath, (LoadContext _) => loadOptions))
{
    converter.Convert(outputPath, new PdfConvertOptions());
}

return audit.Loaded;
```

**Advantages:**
- Simplest constructor overload
- Keeps a usable file path for logging or re-processing

**Limitations:**
- Loads anything already sitting in the same folder
- That's exactly how `other-customer-signature.svg` got into `from-path.pdf`

## Method 2: ConvertUploadFromStream

**Overview:** Converts the identical invoice, changing only how the file
is opened.

#### How It Works

Swapping `uploadPath` for `() => File.OpenRead(uploadPath)` removes the
base folder entirely. No folder means no "already inside it" exception. A
relative reference no longer points into a folder the document owns, so
it is blocked along with every remote one.

#### When to Use

- ✅ The upload lives in a folder shared with other uploads
- ✅ You don't need a file-system path after conversion
- ❌ Not suited to: an upload that must load images stored beside it

#### Implementation

```csharp
var audit = new ResourceAudit();
var loadOptions = new WebLoadOptions { ExternalResourceHandler = audit };

using (var converter = new Converter(
    () => File.OpenRead(uploadPath), (LoadContext _) => loadOptions))
{
    converter.Convert(outputPath, new PdfConvertOptions());
}

return audit.Loaded;
```

**Advantages:**
- One constructor change closes the same-folder gap

**Limitations:**
- Drops the convenience of a file-system path for later steps

## Method 3: ConvertWithTrustedAsset

**Overview:** Converts the invoice while supplying its logo from a file
you control, instead of letting it be requested.

#### How It Works

A dictionary of trusted URLs maps each one to local bytes. Inside
`OnLoading`, a match sets `Data` to those bytes and `Skipped` to `false`.
No request goes out. Every other reference in the invoice still gets the
stream-input treatment from Method 2.

#### When to Use

- ✅ One or two specific assets (a logo, a letterhead) need to render
- ✅ You already have a reviewed copy of that asset on disk
- ❌ Not recommended for: assets you haven't reviewed yourself

#### Implementation

```csharp
var trustedAssets = new Dictionary<string, byte[]>
{
    [assetUrl] = File.ReadAllBytes(assetPath)
};
var audit = new ResourceAudit(trustedAssets);
var loadOptions = new WebLoadOptions { ExternalResourceHandler = audit };

using (var converter = new Converter(
    () => File.OpenRead(uploadPath), (LoadContext _) => loadOptions))
{
    converter.Convert(outputPath, new PdfConvertOptions());
}

return audit.Loaded;
```

**Advantages:**
- The logo renders without any network request
- Every other reference stays denied by default

**Limitations:**
- Only covers URLs you've listed in advance

## Method 4: ConvertSvgUpload

**Overview:** Converts an SVG drawing instead of HTML, using
`SvgLoadOptions` in place of `WebLoadOptions`.

#### How It Works

`SvgLoadOptions` is what GroupDocs.Conversion selects for SVG and SVGZ
input by default, and the same `ExternalResourceHandler` contract applies
to its `<image>` references. The drawing's own inline script does not
run, either.

#### When to Use

- ✅ The upload is SVG rather than HTML or an e-mail format
- ✅ You want the identical audit pattern across formats
- ❌ Not recommended for: relying on `Data` substitution when the SVG is
  converted to XPS or a spreadsheet

#### Implementation

```csharp
var audit = new ResourceAudit();
var loadOptions = new SvgLoadOptions { ExternalResourceHandler = audit };

using (var converter = new Converter(
    () => File.OpenRead(uploadPath), (LoadContext _) => loadOptions))
{
    converter.Convert(outputPath, new PdfConvertOptions());
}

return audit.Loaded;
```

**Advantages:**
- Same `ResourceAudit` class, unmodified, works for both formats

**Limitations:**
- `Data` substitution doesn't apply to every SVG output format

## Method 5: RejectLooseWhitelistEntry

**Overview:** Shows what happens when a `WhitelistedResources` entry is a
bare host name instead of an absolute URI prefix.

#### How It Works

`WhitelistedResources` expects each entry to be an absolute prefix, such
as `https://cdn.example.com/brand/`. Pass `cdn.example.com` alone and the
load fails with `InvalidLoadOptionsException`. The message names the bad
entry so you can fix it immediately.

#### When to Use

- ✅ Validating a whitelist entry before it reaches production
- ✅ Writing a startup check that exercises real `WhitelistedResources` values
- ❌ Not a conversion technique on its own - it's a configuration guard

#### Implementation

```csharp
var loadOptions = new WebLoadOptions
{
    WhitelistedResources = new List<string> { entry }
};

try
{
    using var converter = new Converter(
        () => File.OpenRead(uploadPath), (LoadContext _) => loadOptions);
    converter.Convert("output/loose-whitelist.pdf", new PdfConvertOptions());
    return null;
}
catch (InvalidLoadOptionsException exception)
{
    return exception.Message;
}
```

**Advantages:**
- Fails at conversion time with a message that names the bad entry

**Limitations:**
- Only catches entries you actually exercise with real input

The message is exact: `Whitelisted resource 'cdn.example.com' is not
valid. Expected an absolute URI prefix without a query, fragment or
encoded '/', '\' or '.', such as 'https://cdn.example.com/assets/' or
'file:///C:/assets/'.`

## Common Pitfalls and How to Avoid Them

1. **Converting a shared folder's uploads by path**
   - **Problem:** a relative reference inside one upload resolves to a
     different file sitting in the same folder.
   - **Solution:** use Method 2 (stream input) for anything saved outside
     a dedicated per-upload folder.

2. **Whitelisting a bare host name**
   - **Problem:** `cdn.example.com` is not an absolute URI prefix, so the
     conversion throws instead of matching what you meant.
   - **Solution:** write the full prefix, such as
     `https://cdn.example.com/brand/`, and verify it with Method 5 first.

3. **Enabling `ExecuteScripts` out of habit**
   - **Problem:** it runs the scripts inside the document, a switch meant
     for documents you trust and author yourself.
   - **Solution:** leave it off for anything a user submitted.

## FAQ

**Q: Does `SkipExternalResources = false` make any of this unnecessary?**
A: No - it removes the default denial for every external reference, not
only the ones you intend to allow. Keep it at its default and whitelist
or handle only the resources you actually want.

**Q: Why does a bare host name no longer work as a whitelist entry?**
A: Earlier versions matched an entry wherever it appeared in the URL.
Since 26.10 each entry is the absolute prefix of a trusted location,
without a query, fragment, or encoded `/`, `\`, or `.` - and Method 5
shows a bare host name failing that rule.

**Q: Do UNC paths ever load, even with `SkipExternalResources = false`?**
A: No. UNC references never load, regardless of how
`SkipExternalResources` or `WhitelistedResources` are set.

## Notes

`OnLoading` can run on several threads at once during one conversion, so
any state it touches must be thread-safe - `ResourceAudit` uses a
`ConcurrentQueue<string>` for exactly that reason. A handler that throws
becomes a `GroupDocsConversionException` wrapping your exception. When we
first ran this sample from a file path, the other customer's signature
sat right there in `from-path.pdf`. Method 2 exists because of that run.

## Conclusion

Default to a stream. Everything else - a trusted asset, a whitelist entry,
an SVG instead of HTML - is a deliberate exception you write into the
code, not a surprise you find in the output.

## See Also

- [In-depth blog article about this project](https://blog.groupdocs.com/conversion/convert-untrusted-uploads-safely-net/)
- [Skip loading of external resources](https://docs.groupdocs.com/conversion/net/skip-loading-external-resources/)
- [Network access and data privacy](https://docs.groupdocs.com/conversion/net/network-access-and-data-privacy/)
- [GroupDocs.Conversion for .NET documentation](https://docs.groupdocs.com/conversion/net/)
- [API Reference](https://reference.groupdocs.com/conversion/net/)
- [secure-untrusted-document-upload-conversion-dotnet on GitHub](https://github.com/groupdocs-conversion/secure-untrusted-document-upload-conversion-dotnet)
