---
id: skip-loading-external-resources
url: conversion/net/skip-loading-external-resources
title: Skip loading of external resources
weight: 4
description: "Learn how GroupDocs.Conversion for .NET denies external resources by default, and how to allow trusted resources by absolute URI prefix, decide per resource with a handler, migrate whitelist entries from earlier versions, run scripts and handle XBRL and 3D dependencies."
keywords: Restrict loading of external resources during conversion, external resources, Skip loading of external resources during conversion, Loading external resources, WhitelistedResources, SkipExternalResources, ExternalResourceHandler, IExternalResourceHandler, ExecuteScripts, SSRF
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## What are external resources?

*External resources* are content a document references instead of carrying: images, stylesheets, fonts, scripts, linked workbooks, schemas, textures and similar files. [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) treats any resource that a document tries to load from a URL or from a file outside the document as external.

## Security considerations

Loading external resources from untrusted documents can pose security risks:

* **Server-Side Request Forgery (SSRF)**: a malicious document can reference internal network addresses, such as cloud metadata endpoints or `localhost` services, and make your server request them.
* **NTLM credential leaks**: a reference to a UNC path (for example `\\server\share`) can trigger automatic NTLM authentication and leak credentials.
* **Data exfiltration and tracking**: a request to an attacker's server reveals that, when and where a document was opened.
* **Local file disclosure**: a reference to a local file, such as `file:///etc/passwd`, can pull content from the machine into the output.

To mitigate these risks, **GroupDocs.Conversion** is **secure by default**: the `SkipExternalResources` property is `true` in every load options class that supports it, so nothing external is loaded unless you allow it.

## What loads by default

With `SkipExternalResources` set to `true` (the default), a document still loads:

* content it carries: `data:` URIs, `cid:` references, MHTML parts and packaged media;
* `about:` and `base64` references;
* local files inside the base directory;
* resources that match an entry of `WhitelistedResources`.

Everything else is skipped and the conversion continues: `http`, `https`, `ftp` and every other scheme, local files outside the base directory, and relative references that leave it through `../`.

The **base directory** is `WebLoadOptions.BasePath` when the options are `WebLoadOptions` and it names a local directory. Otherwise it is the folder of the source file when the document is converted from a file path, and there is none when it is converted from a stream. An `http` or `https` `BasePath`, a UNC `BasePath` and a source file on a UNC share give no base directory. Symbolic links and junctions inside the base directory are not resolved, so it should hold only content you trust.

UNC paths (`\\host\share`, `//host/share`, `file://host/share` and their other forms) are never loaded, whatever the options are set to.

The options are read when an operation such as `Convert` or `GetDocumentInfo` loads the document. Changing them while that operation runs does not affect it.

{{< alert style="info" >}}
Since version 26.10, local files outside the base directory are denied by default, and UNC paths are never loaded, even when `SkipExternalResources` is `false`. Earlier versions loaded local files while external resources were denied, and blocked UNC paths only while they were denied.
{{< /alert >}}

## Supported document types

The control is available through these load options classes. All of them implement the [IResourceLoadingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/iresourceloadingoptions/) interface, which defines `SkipExternalResources` and `WhitelistedResources`.

| Load options class | Source formats |
|--------------------|----------------|
| [WebLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/) | HTML, HTM, MHT, MHTML, CHM, JSON |
| [XmlLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/) | XML (derives from `WebLoadOptions`) |
| [WordProcessingLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/) | DOC, DOCX, DOCM, DOT, DOTX, DOTM, RTF, ODT, OTT, FOPCT, MD |
| [SpreadsheetLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/) | XLS, XLSX, XLSM, XLSB, XLT, XLTX, XLTM, XLAM, ODS, OTS, FODS, SXC, FOPCS, NUMBERS |
| [CsvLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/) | CSV (derives from `SpreadsheetLoadOptions`) |
| [TsvLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/tsvloadoptions/) | TSV (derives from `SpreadsheetLoadOptions`) |
| [PresentationLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/) | PPT, PPTX, PPTM, PPS, PPSX, PPSM, POT, POTX, POTM, ODP, OTP, FODP |
| [EmailLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/) | EML, EMLX, MSG, ICS |
| [SvgLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/) | SVG, SVGZ |
| [FinanceLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/) | XBRL, iXBRL |
| [ThreeDLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/threedloadoptions/) | FBX, OBJ, GLTF, GLB, 3DS, DAE, 3MF, AMF, ASE, DRC, JT, MA, MB, PLY, RVM, U3D, USD, USDZ, VRML, X |

Other formats have no switch:

* Raster images, audio, fonts and plain text have no way to reference an external resource.
* For PDF, XPS, PostScript, EPUB, CAD drawings, Visio diagrams, OneNote, mailboxes such as PST and MBOX, GIS formats and others, the product's tests convert a probe document full of external references and observe no request.
* CorelDRAW, Publisher, Photoshop documents with linked layers and indirect DjVu documents are not covered by that measurement.
* An archive converts each entry as its own source format, under that format's load options.
* Video is never parsed in the process; it is converted only by the video connector you supply.

{{< alert style="info" >}}
`FinanceLoadOptions` and `ThreeDLoadOptions` support external resource control since version 26.10.
{{< /alert >}}

## Allowing trusted resources

To load particular resources from trusted sources while everything else stays denied, add their **absolute URI prefixes** to `WhitelistedResources`. The whitelist takes effect only while `SkipExternalResources` is `true`.

A resource matches an entry when:

* its scheme and host equal the entry's, ignoring case, with no subdomain matching;
* its port equals the entry's once the scheme's default port is filled in;
* its path starts with the entry's path at a `/` boundary, case-sensitively, so `/assets` does not match `/assetsX`.

The resource is resolved against its base first. Local paths become `file:` URIs, dot segments are removed, and the query and fragment are ignored. A resource holding an encoded `/`, `\` or `.` never matches.

The following example loads images and stylesheets from one CDN folder and from one local folder, and denies everything else:

```csharp
WebLoadOptions loadOptions = new WebLoadOptions
{
    WhitelistedResources = new List<string>
    {
        "https://cdn.example.com/assets/",
        "file:///C:/assets/"
    }
};
using (Converter converter = new Converter("sample.html", (LoadContext loadContext) => loadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

An entry that is null, empty, not an absolute URI, carries a query or fragment, or contains `%2F`, `%5C` or `%2E` makes the load fail with [InvalidLoadOptionsException](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.exceptions/invalidloadoptionsexception/), whatever `SkipExternalResources` is set to.

{{< alert style="warning" >}}
Since version 26.10, each entry is an absolute URI prefix. Earlier versions matched entries as fragments of the URL, so entries such as `jpg`, `.png` or `example.com` were accepted. Such entries now make the load fail with `InvalidLoadOptionsException`. See [Migrating whitelist entries from earlier versions](#migrating-whitelist-entries-from-earlier-versions).
{{< /alert >}}

Keep in mind:

* a UNC resource never loads, even when an entry matches it;
* the engine follows redirects: a whitelisted URL that redirects loads the redirect target, even when the target is not whitelisted;
* the list is copied when the document loads, and a null list counts as empty.

To decide per resource in code, for example by file type, use a [handler](#deciding-per-resource-with-a-handler).

## Migrating whitelist entries from earlier versions

Before version 26.10, a resource matched an entry when the entry appeared anywhere in its URL. That match did not limit the host: an entry such as `jpg` also matched `http://169.254.169.254/latest/meta-data/?jpg` or `http://jpg.attacker.example/image.png`. Version 26.10 requires each entry to be the absolute URI prefix of a location you trust.

| Entry before 26.10 | What it matched | Replacement since 26.10 |
|--------------------|-----------------|-------------------------|
| `example.com` | Any URL containing the text, including `https://example.com.attacker.example/` | `https://example.com/`. Add an entry for each scheme and subdomain you trust, such as `http://example.com/` or `https://images.example.com/`. |
| `cdn.example.com/images` | Any URL containing the text | `https://cdn.example.com/images/` |
| `jpg`, `.png` and other file types | Any URL containing the text, on any host | No whitelist equivalent. Whitelist the locations the images come from, or use a [handler](#deciding-per-resource-with-a-handler) that checks both the location and the file type. |
| `C:\assets` | Local paths containing the text | `file:///C:/assets/`. Files inside the document's own folder need no entry. |
| `\\server\share` | UNC paths containing the text | No replacement: UNC paths never load. Copy the files into the document's folder or a whitelisted local folder, or serve them over `https` and whitelist that prefix. |

## Deciding per resource with a handler

When a list of prefixes is not enough — to allow resources by file type, to record every resource a document references, or to supply a resource's content yourself — set the `ExternalResourceHandler` property of the load options to your implementation of `IExternalResourceHandler`. The property is available on every load options class listed in [Supported document types](#supported-document-types) and is `null` by default.

For each resource the engine is about to load:

1. `SkipExternalResources` and `WhitelistedResources` decide first, as described above.
2. The handler's `OnLoading` method is called with an `ExternalResourceLoadingArgs`. Its `Uri` property holds the reference, and `Skipped` holds the decision from step 1.
3. The handler can keep that decision, set `Skipped` to `false` to load the resource, set it to `true` to skip it, or set `Data` to supply the resource's content. When `Data` is set and `Skipped` is `false`, the engine uses those bytes and makes no request for the resource; an empty array supplies empty content.

### Allowing images by file type

The following handler loads JPEG images from one trusted host in addition to what the defaults allow. Everything else keeps the decision of step 1, so content the document carries and local files inside its folder still load.

```csharp
public class TrustedJpegHandler : IExternalResourceHandler
{
    public void OnLoading(ExternalResourceLoadingArgs args)
    {
        Uri uri;
        if (Uri.TryCreate(args.Uri, UriKind.Absolute, out uri)
            && uri.Scheme == Uri.UriSchemeHttps
            && string.Equals(uri.Host, "cdn.example.com", StringComparison.OrdinalIgnoreCase)
            && (uri.AbsolutePath.EndsWith(".jpg", StringComparison.OrdinalIgnoreCase)
                || uri.AbsolutePath.EndsWith(".jpeg", StringComparison.OrdinalIgnoreCase)))
        {
            args.Skipped = false;
        }
    }
}
```

```csharp
WebLoadOptions loadOptions = new WebLoadOptions
{
    ExternalResourceHandler = new TrustedJpegHandler()
};
using (Converter converter = new Converter("sample.html", (LoadContext loadContext) => loadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

Check the location as well as the file type. A URL that ends in `.jpg` can point at any server, including `http://169.254.169.254/image.jpg`, and says nothing about the content it returns.

### Supplying content and recording resources

The following handler supplies resources from content you have already downloaded and verified, and records the decision for every resource:

```csharp
public class PrefetchedResourceHandler : IExternalResourceHandler
{
    private readonly IReadOnlyDictionary<string, byte[]> _prefetched;

    public PrefetchedResourceHandler(IReadOnlyDictionary<string, byte[]> prefetched)
    {
        _prefetched = prefetched;
    }

    public void OnLoading(ExternalResourceLoadingArgs args)
    {
        byte[] content;
        if (_prefetched.TryGetValue(args.Uri, out content))
        {
            args.Data = content;
            args.Skipped = false;
        }
        Console.WriteLine("{0}: {1}", args.Skipped ? "skipped" : "loaded", args.Uri);
    }
}
```

### Rules for handlers

* `Uri` is the location the engine is about to load. For word processing, presentation, HTML and SVG documents it is usually already resolved against the document's base, so it is the URL that would be requested. For other formats it is the reference as the document carries it, so it can be relative.
* The handler is also called for content the document carries, such as `data:` URIs and `cid:` parts, with `Skipped` set to `false`. Skipping such a resource removes it from the output.
* UNC paths and `javascript:` or `vbscript:` references are offered with `Skipped` set to `true` and never load, whatever the handler sets.
* While `ExecuteScripts` is `false`, no script file is offered to the handler.
* The same resource can be offered more than once in one conversion, for example an image in an HTML page converted to a spreadsheet. It loads only when every call allows it, and the content supplied on the last call is used.
* When converting XSL-FO documents, SVG documents to XPS or spreadsheet formats, and e-mail messages to spreadsheet formats, the handler can allow or skip a resource, but `Data` has no effect. For XBRL and inline XBRL documents the handler can only skip a reference; see [XBRL and inline XBRL](#xbrl-and-inline-xbrl).
* While `SkipExternalResources` is `true`, the document type declaration (`<!DOCTYPE>`) of an XML-based document, such as an SVG or XSL-FO document, is removed before it is converted. Its external DTD and external entities are offered with `Skipped` set to `true`, and the declaration is kept only when the handler allows each of them. A declaration with neither is removed without being offered.
* If the handler throws, that resource is skipped, and the operation throws [GroupDocsConversionException](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.exceptions/groupdocsconversionexception/) with your exception as `InnerException`.
* The handler can be called from several threads at once, so it must be thread-safe.
* A handler that allows everything reopens every request the defaults deny. Decide from the URI, never from content of the document being converted.

{{< alert style="info" >}}
`ExternalResourceHandler` is available since version 26.10.
{{< /alert >}}

## Loading all external resources

If you convert only documents you trust, you can allow every external resource by setting `SkipExternalResources` to `false`. UNC paths still never load, the whitelist has no effect, and the engine follows redirects. A [handler](#deciding-per-resource-with-a-handler), when set, is still called and can skip resources.

```csharp
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions
{
    SkipExternalResources = false
};
using (Converter converter = new Converter("trusted-document.docx", (LoadContext loadContext) => loadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Running scripts

`WebLoadOptions`, `XmlLoadOptions` and `SvgLoadOptions` also have an `ExecuteScripts` property, `false` by default.

* When `false`, no script runs, inline or external, and no external script file is requested, whatever `SkipExternalResources` is set to. Content a script would generate is absent from the output.
* When `true`, inline scripts run, and an external script file is a resource like any other: it loads only as `SkipExternalResources` and `WhitelistedResources` allow. Turn it on only for documents you trust.

```csharp
WebLoadOptions loadOptions = new WebLoadOptions
{
    ExecuteScripts = true
};
using (Converter converter = new Converter("trusted-page.html", (LoadContext loadContext) => loadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

{{< alert style="info" >}}
`ExecuteScripts` is available since version 26.10.
{{< /alert >}}

## Format-specific behaviour

### XBRL and inline XBRL

An XBRL or inline XBRL document references its taxonomy: schemas, linkbases and the schemas they import. While `SkipExternalResources` is `true`, the document loads only when every reference in that chain stays inside the document's own folder, which requires converting from a path. A document that references a remote taxonomy, a file outside its folder or any file when loaded from a stream, or whose local chain is not well-formed XML, fails to load with `InvalidLoadOptionsException`. Nearly every published taxonomy is remote, so most filings need `SkipExternalResources` set to `false`:

```csharp
FinanceLoadOptions loadOptions = new FinanceLoadOptions
{
    SkipExternalResources = false
};
using (Converter converter = new Converter("filing.xbrl", (LoadContext loadContext) => loadOptions))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("filing.xlsx", options);
}
```

`WhitelistedResources` is never consulted for XBRL: a whitelisted remote schema is still denied, because the schemas it imports cannot be judged without fetching it. Its entries are still validated. With `SkipExternalResources` set to `false`, every taxonomy file the document needs is loaded, including schemas imported by remote schemas.

A handler set on `FinanceLoadOptions` is called for each taxonomy reference while `SkipExternalResources` is `true`, except references inside the document. It can skip a reference, which makes the load fail as a denied reference does, but it cannot allow a reference that is denied. With `SkipExternalResources` set to `false`, the handler is not called for XBRL documents.

### 3D models

A 3D document can depend on other files: material libraries, textures and external buffers. These dependencies are always read as local files. Remote dependencies never load, even when `SkipExternalResources` is `false`, so an entry of `WhitelistedResources` takes effect only as a `file:` prefix, such as `file:///D:/models/materials/`.

A dependency that is not allowed is treated as missing. A model that cannot load without it, such as a glTF file whose external buffer is denied, fails to load.

## See also

* [Network access and data privacy]({{< ref "conversion/net/getting-started/network-access-and-data-privacy.md" >}})
