---
id: groupdocs-conversion-for-net-23-4-release-notes
url: conversion/net/groupdocs-conversion-for-net-23-4-release-notes
title: GroupDocs.Conversion for .NET 23.4 Release Notes
weight: 21
description: "Features and enhancements introduced in GroupDocs.Conversion for .NET 23.4."
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 5+ features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5358 | Feature | Implement conversion from Finance to Finance formats |
| CONVERSIONNET-5961 | Feature | Implement conversion to Ps |
| CONVERSIONNET-5962 | Feature | Implement conversion to Pcl |
| CONVERSIONNET-5359 | Feature | Implement conversion from Finance to Spreadsheet formats |
| CONVERSIONNET-5956 | Enhancement | Improve Diagram to Spreadsheet conversion |
| CONVERSIONNET-6006 | Bug | Incorrect exception is thrown if the provided source document is missing |
| CONVERSIONNET-3523 | Bug | Convert PDF to PDF/A - File size issue |
| CONVERSIONNET-5952 | Bug | Cannot view output PNG in firefox |
| CONVERSIONNET-5986 | Bug | IsPasswordProtected for pdf document returns true for not protected document |


## Major features

* Conversions from Finance to Finance formats.
* Conversions from Finance to Spreadsheet format.
* Conversions to Ps format.
* Conversions to Pcl format.
* Improved Diagram to Spreadsheet conversions.

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
