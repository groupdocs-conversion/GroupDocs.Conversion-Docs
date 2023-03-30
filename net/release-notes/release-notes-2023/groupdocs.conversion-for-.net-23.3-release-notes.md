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
| CONVERSIONNET-5292 | Feature | Implement GIS to Pdf conversion |
| CONVERSIONNET-5291 | Feature | Implement GIS to Markup conversion |
| CONVERSIONNET-5290 | Feature | Implement GIS to Image conversion |
| CONVERSIONNET-5289 | Feature | Implement GIS to GIS conversion |
| CONVERSIONNET-5295 | Feature | Implement GIS to WordProcessing conversion |
| CONVERSIONNET-5294 | Feature | Implement GIS to Spreadsheet conversion |
| CONVERSIONNET-5293 | Feature | Implement GIS to Presentation conversion |
| CONVERSIONNET-5729 | Enhancement | Improve conversion and compression behavior |
| CONVERSIONNET-5896 | Enhancement | Improve performance of PDF to Image conversions when converting by page |
| CONVERSIONNET-5902 | Enhancement | Improve Svg to Spreadsheet conversion |
| CONVERSIONNET-5864 | Enhancement | Improve Fonts Embedding using FontSubsetStrategy |
| CONVERSIONNET-5866 | Bug | PDF to PNG: Slow conversion |
| CONVERSIONNET-5610 | Bug | Text overlap on images in PDF to DOCX Conversion |
| CONVERSIONNET-5885 | Bug | NullReferenceException when converting dxf files to pdf |
| CONVERSIONNET-5865 | Bug | PDF to PNG: Conversion doesn't finish |

## Major features

* Conversions from GIS to Pdf, Markup, Image, GIS, Wordprocessing, Spreadsheet and Presentation formats.
* Improved conversion and compression behavior when using fluent syntax.
* Improved performance of Pdf to Image conversions when converting by page.

### Improved conversion and compression behavior

Now is possible to convert a document to images by page and compress all generated pages in a archive.
For example to convert a pdf to images by page and compress them in an archive you could use the following snippet:

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

1. Introduced new `GisLoadOptions`  class
2. Removed obsoleted file types which were marked for removal in v23.3
