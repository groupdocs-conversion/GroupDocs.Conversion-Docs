---
id: convert-tiff-to-pdf
url: conversion/net/convert-tiff-to-pdf
title: Convert TIFF to PDF
description: "Transform multi-paged or multi-frame TIFF images to PDF using a few lines of C# code and powerful features of GroupDocs.Conversion for .NET."
keywords: Convert TIFF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIFF or TIF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format. The format is not machine dependent and is free from bounds like processor, operating system, or file systems.

To convert TIFF to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source TIFF file
using (Converter converter = new Converter("sample.tiff"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**TIFF to PDF converter**](https://products.groupdocs.app/conversion/tiff-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIFF to PDF"](conversion/net/images/convert-tiff-to-pdf.png)](https://products.groupdocs.app/conversion/tiff-to-pdf)