---
id: convert-tif-to-pdf
url: conversion/net/convert-tif-to-pdf
title: Convert TIF to PDF
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

To convert from Tagged Image File Format (.tif) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source TIF file
using (Converter converter = new Converter("sample.tif"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to PDF converter**](https://products.groupdocs.app/conversion/tif-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to PDF"](conversion/net/images/convert-tif-to-pdf.png)](https://products.groupdocs.app/conversion/tif-to-pdf)