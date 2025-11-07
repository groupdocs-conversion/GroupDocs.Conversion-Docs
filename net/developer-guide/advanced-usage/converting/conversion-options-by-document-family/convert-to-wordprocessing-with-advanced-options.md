---
id: convert-to-wordprocessing-with-advanced-options
url: conversion/net/convert-to-wordprocessing-with-advanced-options
title: Convert to WordProcessing with advanced options
weight: 8
description: "Follow this guide and learn how to convert documents to Word and Open Document formats like DOC, DOCX, ODT, OTT formats with page size, margins, DPI and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to Word, Convert to WordProcessing, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides the [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions) class to give you control over conversion result when convert to WordProcessing formats. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from base class [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions) has the following additional options:

*   **[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** specifies desired result document type. Available options are: *Doc, Docm, Docx, Dot, Dotx, Rtf, Odt, Ott, Mobi, Txt, Md*.
*   **[PageWidth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/pagewidth)** specifies desired page width in points after conversion (1 point = 1/72 inch). When set, PageSize is automatically changed to Custom.
*   **[PageHeight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/pageheight)** specifies desired page height in points after conversion (1 point = 1/72 inch). When set, PageSize is automatically changed to Custom.
*   **[PageSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/pagesize)** specifies page size. Available options are: *Default, A3, A4, A5, Letter, Legal, Tabloid*.
*   **[PageOrientation](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/pageorientation)** specifies page orientation. Available options are: *Default, Landscape, Portrait*.
*   **[FallbackPageSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/fallbackpagesize)** specifies the fallback page size to use when the input document's page size cannot be determined.
*   **[Dpi](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/dpi)** specifies desired page dpi after conversion. The default resolution is 96 dpi.
*   **[MarginTop](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/margintop)** specifies the desired page top margin in points after conversion.
*   **[MarginBottom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/marginbottom)** specifies the desired page bottom margin in points after conversion.
*   **[MarginLeft](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/marginleft)** specifies the desired page left margin in points after conversion.
*   **[MarginRight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/marginright)** specifies the desired page right margin in points after conversion.
*   **[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/password)** whether the converted document will be password protected with the specified password.
*   **[PdfRecognitionMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/pdfrecognitionmode)** specifies the recognition mode when converting from PDF. Available options are: *Textbox, Flow*. Flow mode is recommended for maximum content editability.
*   **[RtfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/rtfoptions)** specifies RTF specific options. See [below](#rtfoptions).
*   **[MarkdownOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/markdownoptions)** specifies Markdown specific options when converting to Markdown format.
*   **[Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/zoom)** specifies the zoom level in percentage. Default is 100.

The following code snippet shows how to convert to WordProcessing with advanced options:

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Format = WordProcessingFileType.Docx,
        PageOrientation = PageOrientation.Portrait
    };
    converter.Convert("converted.docx", options);
}
```

## Page Size and Dimensions

You can control page size using either predefined sizes or custom dimensions:

### Using Predefined Page Size

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        PageSize = PageSize.A4,
        PageOrientation = PageOrientation.Portrait
    };
    converter.Convert("a4-document.docx", options);
}
```

### Using Custom Dimensions

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        PageWidth = 612,   // 8.5 inches × 72 points/inch
        PageHeight = 792   // 11 inches × 72 points/inch
    };
    converter.Convert("custom-size.docx", options);
}
```

## Page Margins

Set custom margins for all four sides:

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        MarginTop = 72,     // 1 inch
        MarginBottom = 72,  // 1 inch
        MarginLeft = 90,    // 1.25 inches
        MarginRight = 90    // 1.25 inches
    };
    converter.Convert("margins-document.docx", options);
}
```

## PDF Recognition Mode

When converting from PDF, control how content is interpreted:

```csharp
using (Converter converter = new Converter("document.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        PdfRecognitionMode = PdfRecognitionMode.Flow  // Recommended for editable content
    };
    converter.Convert("editable-document.docx", options);
}
```

Available recognition modes:
- **Textbox** - Preserves exact layout using textboxes (less editable)
- **Flow** - Optimizes for content flow and editability (recommended)

### RtfOptions

The [RtfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/rtfoptions) class provides RTF-specific convert options:

*   **ExportImagesForOldReaders** - specifies whether the keywords for "old readers" are written to RTF or not. This can significantly affect the size of the RTF document.

The following code snippet shows how to convert to RTF with specific options:

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        Format = WordProcessingFileType.Rtf,
        RtfOptions = new RtfOptions
        {
            ExportImagesForOldReaders = true
        }
    };
    converter.Convert("converted.rtf", options);
}
```

## Convert to Markdown

Convert documents to Markdown format:

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        Format = WordProcessingFileType.Md
    };
    converter.Convert("converted.md", options);
}
```

## More Resources

- [API Reference: WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
