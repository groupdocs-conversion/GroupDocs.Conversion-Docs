---
id: convert-email-with-attachments-to-pdf
url: conversion/net/use-cases/convert-email-with-attachments-to-pdf
title: Convert email with attachments to PDF
weight: 2
description: "A technical walkthrough of 3 code patterns for converting an Outlook message and its attachments to PDF with GroupDocs.Conversion for .NET, with the trade-offs between them."
keywords: email to PDF, MSG to PDF, EML to PDF, email attachments, EmailLoadOptions, SaveContext, convert attachments to PDF
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

{{< alert style="info" >}}
💡 Full working example available on GitHub:
[convert-email-and-attachments-to-pdf-dotnet](https://github.com/groupdocs-conversion/convert-email-and-attachments-to-pdf-dotnet)
{{< /alert >}}

## Executive Summary

Email-with-attachments conversion is a GroupDocs.Conversion capability for
.NET that turns an Outlook message and its attachments into PDF output,
either as one PDF describing the message or as a separate PDF per item. The
underlying API stays the same across all three patterns below:
`EmailLoadOptions` on the load side, `SaveContext` on the save side. What
changes is which options are set and how the output path gets built.

## What This Guide Covers

This guide walks through `EmailLoadOptions` and `SaveContext` on
`Converter.Convert`, using a sample Outlook `.msg` message and a sample
support `.eml` message as the running examples. Every output named below
comes from running the sample against those two files.

**Prerequisites:**
- .NET SDK 8.0 or later
- GroupDocs.Conversion for .NET 26.10.0 or later

Install the package with NuGet:

```bash
dotnet add package GroupDocs.Conversion --version 26.10.0
```

## Implementation Patterns Overview

Three patterns cover the practical range of this problem. Pattern 1
converts only the message. Pattern 2 converts the message and every
attachment, each as its own file. Pattern 3 adds the handling a real
inbox eventually needs: attachments that share a file name, and
attachments with no route to PDF at all.

| Pattern | Output | `SaveContext` needed | Name clashes | Unsupported attachments |
|---------|--------|----------------------|---------------|--------------------------|
| Message only | 1 PDF | No | Not applicable | Not applicable |
| Message and every attachment | One PDF per item | Yes | Needs `ItemIndex` | Not handled |
| Duplicates and no-route attachments | One PDF per item, plus pass-through files | Yes | Handled via `ItemIndex` | Handled via `TargetFormat` |

## Pattern 1: Message Only

### Design Overview

This is the simplest of the three. `EmailLoadOptions.ConvertOwner` set to
`true` and `ConvertOwned` set to `false` treats the message as the only
thing worth converting. Attachments appear by name only.

### Implementation

```csharp
var loadOptions = new EmailLoadOptions
{
    ConvertOwner = true,
    ConvertOwned = false
};
```

```csharp
using (var converter = new Converter(messagePath, (LoadContext _) => loadOptions))
{
    converter.Convert(outputPath, new PdfConvertOptions());
}
```

### Technical Notes

A plain output path is enough here. No callback is involved. Running this
against the sample Outlook message produces a one-page PDF whose header
lists `From`, `Sent`, `To`, `Subject` and `Attachments`, followed by the
body. The trade-off is simple: smaller output, but the attachment content
never reaches a page.

## Pattern 2: Message and Every Attachment

### Design Overview

Setting both `ConvertOwner` and `ConvertOwned` to `true`, with `Depth`
left at its default of `2`, makes the converter call back once per output
item instead of writing to one fixed path. `SaveContext.ItemIndex` starts
at 1 for the message and counts up for each attachment that follows.

Two attachments, three files. The sample Outlook message carries an image
and a Word document, and the message itself is item one, not item zero.

### Implementation

```csharp
var loadOptions = new EmailLoadOptions
{
    ConvertOwner = true,
    ConvertOwned = true,
    Depth = 2
};
int written = 0;
```

```csharp
using (var converter = new Converter(messagePath, (LoadContext _) => loadOptions))
{
    converter.Convert((SaveContext item) =>
    {
        written++;
        string name = $"{item.ItemIndex:D2}-{item.SourceFileName}.pdf";
        return File.Create(Path.Combine(outputFolder, name));
    }, new PdfConvertOptions());
}
```

### Technical Notes

`SaveContext.HierarchyLevel` is 0 for the message and 1 for an
attachment. That one field is enough to tell the two apart inside the
callback. Point this pattern at the sample Outlook message, and the
message lands first, then the image attachment, then the Word
attachment, one call for each.

## Pattern 3: Duplicates and No-Route Attachments

### Design Overview

Two attachments can carry the same file name. One attachment can have no
conversion route to PDF at all. Pattern 3 handles both by reading two
fields off `SaveContext` instead of one: `ItemIndex` for naming, and
`TargetFormat` for deciding whether to convert at all.

### Where do two identically named attachments end up on disk?

Each one keeps its own numbered file. The sample support e-mail attaches
two files both called `report.csv`; the first becomes `02-report.csv.pdf`
and the second becomes `03-report.csv.pdf`, prefixed by their distinct
`ItemIndex` values. Neither file touches the other on disk, even though
the two source names are identical.

### Implementation

```csharp
var loadOptions = new EmailLoadOptions { ConvertOwner = true, ConvertOwned = true };
int keptAsTheyAre = 0;
```

```csharp
using (var converter = new Converter(messagePath, (LoadContext _) => loadOptions))
{
    converter.Convert((SaveContext item) =>
    {
        bool passedThrough = item.TargetFormat == FileType.Unknown;
        string baseName = $"{item.ItemIndex:D2}-{item.SourceFileName}";
        string name = passedThrough
            ? baseName
            : $"{baseName}.{item.TargetFormat.Extension}";
        keptAsTheyAre += passedThrough ? 1 : 0;
        return File.Create(Path.Combine(outputFolder, name));
    }, new PdfConvertOptions());
}
```

### Technical Notes

`item.TargetFormat == FileType.Unknown` is the one check that separates
this pattern from Pattern 2. When it is true, the item is handed back
unconverted. Diffing the kept attachment against the saved file turns up
nothing: all 32 bytes match. The sample's console marks every item as
`converted` or `kept`, so the run log alone shows which attachment stayed
in its original format.

## Operational Considerations

Wrap every `Converter` in a `using` block. It implements `IDisposable`,
and all three patterns share this requirement equally. Build output paths with
`Path.Combine` rather than string concatenation, so the file names stay
correct regardless of which operating system runs the console app. Run the
sample from its project folder: the inputs are read from the relative
`resources/` folder, the message-only PDF lands in `output/`, and the
other two patterns each write to a subfolder of their own.

## Real-World Use Cases

**Support case archiving.** A support team receives e-mails with several
spreadsheet attachments that need to be filed and searched independently
of the message. Pattern 2 turns the message and every attachment into a
separately indexable PDF, named from `ItemIndex` and `SourceFileName`.

**Mixed-format support inbox.** An inbox mixes CSV reports with an
occasional capture file that has no conversion route to PDF. Pattern 3
converts every CSV attachment, keeps duplicate names separate, and lets
the unsupported attachment survive the run under its own name.

## Common Pitfalls

1. Naming outputs from `SourceFileName` alone. Two attachments with the
   same name overwrite each other; always include `ItemIndex` in the
   output file name instead.
2. Assuming every attachment becomes a PDF. An attachment with no route
   to PDF is handed back unchanged, so code that always appends `.pdf`
   saves its original bytes under a misleading name. Branch on
   `item.TargetFormat == FileType.Unknown` first.
3. Leaving `Depth` implicit. It limits how far attachments inside
   attached messages are followed, so set it explicitly when attached
   messages carry attachments of their own.

## Notes

`EmailLoadOptions` defaults to `ConvertOwner = true`, `ConvertOwned = true`
and `Depth = 2`. For a passed-through item `TargetFormat` is
`FileType.Unknown`, so its name comes from `SourceFileName` alone.

## FAQ

**Q: Which pattern should I start with?**
A: Pattern 1 for a message-only record. Move to Pattern 2 once any
attachment needs its own PDF, and add Pattern 3's `TargetFormat` check
once the inbox can contain a format GroupDocs.Conversion cannot route to
PDF.

**Q: Can the three patterns run side by side in the same program?**
A: Yes. They are independent `Converter` calls over the same input file,
so nothing stops a program from running Pattern 1 for a summary PDF and
Pattern 3 for the full breakdown in the same request.

**Q: What happens to an attachment that cannot be converted to PDF?**
A: Since GroupDocs.Conversion for .NET 26.10, it no longer stops the
conversion. The callback still receives it, `TargetFormat` equal to
`FileType.Unknown`. In 26.9 this failed the whole message with a
`ConversionNotSupportedException`.

**Q: Is a license required to run these patterns?**
A: Without one the sample runs in evaluation mode, with its limits. Apply
a GroupDocs.Conversion license, or request a
[temporary license](https://purchase.groupdocs.com/temp-license/100032)
while testing.

## Conclusion and Recommendations

All three patterns sit on the same two building blocks: `EmailLoadOptions`
for what gets converted, `SaveContext` for how each output is named. Start
with whichever pattern matches today's requirement, and move to the next
one only when the inbox actually demands it. There is no benefit to
building Pattern 3's handling before a duplicate name or an unsupported
format shows up in real data.

## See Also

- [In-depth blog article about this project](https://blog.groupdocs.com/conversion/convert-email-with-attachments-to-pdf-net/)
- [Load options for e-mail documents](https://docs.groupdocs.com/conversion/net/load-email-document-with-options/)
- [Converting each email attachment to a different format](https://docs.groupdocs.com/conversion/net/convert-each-email-attachment-to-different-format/)
- [GitHub repository](https://github.com/groupdocs-conversion/convert-email-and-attachments-to-pdf-dotnet)
- [GroupDocs.Conversion for .NET documentation](https://docs.groupdocs.com/conversion/net/)
