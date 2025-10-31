---
id: convert-to-page-description-language-with-advanced-options
url: conversion/net/convert-to-page-description-language-with-advanced-options
title: Convert to Page Description Language formats with advanced options
weight: 20
description: "Learn about PageDescriptionLanguageConvertOptions class for PDL file formats (SVG, XPS, EPS, PS, PCL, TEX) in GroupDocs.Conversion for .NET."
keywords: Convert to SVG, Convert to XPS, Convert to EPS, PDL conversion, Page Description Language
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [PageDescriptionLanguageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pagedescriptionlanguageconvertoptions) class to specify Page Description Language (PDL) file format conversion settings. This class implements [IPagedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions), [IPageRangedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagerangedconvertoptions), and [IWatermarkedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/iwatermarkedconvertoptions) for page selection, page range specification, and watermark support.

## Supported Page Description Language Formats

The following PDL (Page Description Language) formats are supported:

| Format | Extension | Description |
|--------|-----------|-------------|
| **SVG** | .svg | Scalable Vector Graphics (XML-based vector format) |
| **SVGZ** | .svgz | Compressed SVG using GZIP |
| **XPS** | .xps | XML Paper Specification (Microsoft) |
| **OXPS** | .oxps | Open XML Paper Specification |
| **EPS** | .eps | Encapsulated PostScript |
| **PS** | .ps | PostScript Document |
| **PCL** | .pcl | Printer Command Language (HP) |
| **TEX** | .tex | LaTeX Source Document |
| **CGM** | .cgm | Computer Graphics Metafile |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired PDL file format. Available options are: *Svg, Svgz, Xps, Oxps, Eps, Ps, Pcl, Tex, Cgm*.

**[Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pagedescriptionlanguageconvertoptions/width)** - Sets the desired page width in pixels.

**[Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pagedescriptionlanguageconvertoptions/height)** - Sets the desired page height in pixels.

**[PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagenumber)** - Specifies the starting page number for conversion.

**[PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagescount)** - Specifies the number of pages to convert.

**[Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagerangedconvertoptions/pages)** - Specifies a list of specific page numbers to convert.

**[Watermark](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/iwatermarkedconvertoptions/watermark)** - Applies a watermark to the converted document.

## Conversion Examples

PageDescriptionLanguageConvertOptions supports conversion between PDL formats. The following examples demonstrate common conversions.

### XPS to SVG

Convert an XPS document to SVG (Scalable Vector Graphics):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "document.xps";
string outputFile = "document.svg";

using (var converter = new Converter(sourceFile))
{
    var options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg
    };
    converter.Convert(outputFile, options);
}
```

### EPS to XPS

Convert an EPS (Encapsulated PostScript) file to XPS:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "illustration.eps";
string outputFile = "illustration.xps";

using (var converter = new Converter(sourceFile))
{
    var options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Xps
    };
    converter.Convert(outputFile, options);
}
```

### PostScript to SVG

Convert a PostScript (PS) file to SVG:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "print-file.ps";
string outputFile = "print-file.svg";

using (var converter = new Converter(sourceFile))
{
    var options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg
    };
    converter.Convert(outputFile, options);
}
```

## Custom Dimensions

Control output page dimensions using Width and Height properties:

### Using Custom Page Dimensions

Define custom page width and height in pixels:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "technical-diagram.xps";
string outputFile = "technical-diagram.svg";

using (var converter = new Converter(sourceFile))
{
    var options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg,
        Width = 800,   // Width in pixels
        Height = 600   // Height in pixels
    };
    converter.Convert(outputFile, options);
}
```

## Watermark Support

Add text or image watermarks to converted documents:

### Adding Text Watermark

Apply a text watermark to the converted document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "confidential.xps";
string outputFile = "confidential.svg";

using (var converter = new Converter(sourceFile))
{
    var options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg,
        Watermark = new WatermarkTextOptions("CONFIDENTIAL")
        {
            Color = System.Drawing.Color.Red,
            Width = 200,
            Height = 50,
            Top = 100,
            Left = 100
        }
    };
    converter.Convert(outputFile, options);
}
```

## Format Support Notes

PDL to PDL conversions are supported for most format combinations:
- XPS → SVG, EPS, PS, PCL, TEX
- EPS → SVG, XPS, PS, PCL, TEX
- PS → SVG, XPS, EPS, PCL, TEX
- SVG → XPS, EPS, PS, PCL, TEX
- TEX → SVG, XPS, EPS, PS, PCL
- PCL → SVG, XPS, EPS, PS, TEX

**Note:** To convert FROM PDL formats to PDF or images, use [PdfConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-pdf-with-advanced-options.md" >}}) or [ImageConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-image-with-advanced-options.md" >}}).

## More Resources

- [API Reference: PageDescriptionLanguageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pagedescriptionlanguageconvertoptions)
- [API Reference: PageDescriptionLanguageFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/pagedescriptionlanguagefiletype)
- [Convert Page Description Language Formats]({{< ref "conversion/net/developer-guide/basic-usage/convert/page-description-language.md" >}})
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
