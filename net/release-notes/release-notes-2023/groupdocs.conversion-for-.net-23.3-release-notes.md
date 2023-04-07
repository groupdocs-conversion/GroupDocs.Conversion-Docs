---
id: groupdocs-conversion-for-net-23-3-release-notes
url: conversion/net/groupdocs-conversion-for-net-23-3-release-notes
title: GroupDocs.Conversion for .NET 23.3 Release Notes
weight: 22
description: "Features and enhancements introduced in GroupDocs.Conversion for .NET 23.3."
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 10+ features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;5292 | Feature | [Implement GIS to PDF conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5291 | Feature | [Implement GIS to Markup conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5290 | Feature | [Implement GIS to Image conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5289 | Feature | [Implement GIS to GIS conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5295 | Feature | [Implement GIS to WordProcessing conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5294 | Feature | [Implement GIS to Spreadsheet conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5293 | Feature | [Implement GIS to Presentation conversion](#conversions-of-gis-formats) |
| CONVERSIONNET&#8209;5729 | Enhancement | [Improve conversion and compression behavior](#improved-conversion-and-compression-behavior) |
| CONVERSIONNET&#8209;5896 | Enhancement | Improve performance of PDF to Image conversions when converting by page |
| CONVERSIONNET&#8209;5902 | Enhancement | Improve SVG to Spreadsheet conversion |
| CONVERSIONNET&#8209;5864 | Enhancement | Improve Fonts Embedding using FontSubsetStrategy |
| CONVERSIONNET&#8209;5866 | Fix | PDF to PNG: Slow conversion |
| CONVERSIONNET&#8209;5610 | Fix | Text overlap on images in PDF to DOCX Conversion |
| CONVERSIONNET&#8209;5885 | Fix | NullReferenceException when converting DXF files to PDF |
| CONVERSIONNET&#8209;5865 | Fix | PDF to PNG: Conversion doesn't finish |

## Major features

* Conversions from GIS to PDF, Markup, Image, GIS, Wordprocessing, Spreadsheet and Presentation formats.
* Improved conversion and compression behavior when using fluent syntax.
* Improved performance of PDF to Image conversions when converting by page.

### Conversions of GIS formats
Support for GIS (Geographic Information System) formats was added. You can now [convert GIS format]({{< ref "conversion/net/developer-guide/basic-usage/convert/gis.md" >}}) to another GIS format, or another format family - PDF, Markup, Image, Word-processing, Spreadsheet or Presentation. 
For example, the following code sample demonstrates how to convert a GPX file to KML:

```csharp
// Load the source GPX file
using (Converter converter = new Converter("sample.gpx"))
{
    // Set the convert options for KML format
    var options = new GisConvertOptions {
        Format = GisFileType.Kml;
    };
    // Convert to KML format
    converter.Convert("converted.kml", options);
}
```

### Improved conversion and compression behavior

Now is possible to convert a document to images by page and compress all generated pages into an archive.
For example, to convert a PDF to images by page and compress them into an archive you could use the following snippet:

```csharp
var converter = new Converter();

converter.Load("sample.pdf")
    .ConvertByPageTo(p => new MemoryStream()).WithOptions(new ImageConvertOptions
    {
        Format = ImageFileType.Png
    })
    .Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip }).OnCompressionCompleted(
        compressedStream =>
        {
            using (var fs = new FileStream("converted.zip", FileMode.Create))
            {
                compressedStream.CopyTo(fs);
            }
        })
    .Convert();
```

## Public API and backward incompatible changes

1. Introduced new [`GisLoadOptions`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/gisloadoptions/), [`GisConvertOptions`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/gisconvertoptions/) and [`GisFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/gisfiletype/) classes.
2. Removed obsolete file types that were marked for removal in v23.3.
