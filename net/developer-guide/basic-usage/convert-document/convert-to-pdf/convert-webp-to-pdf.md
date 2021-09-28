---
id: convert-webp-to-pdf
url: conversion/net/convert-webp-to-pdf
title: Convert WEBP to PDF
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

To convert from Raster Web Image File Format (.webp) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source WEBP file
using (Converter converter = new Converter("sample.webp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to PDF converter**](https://products.groupdocs.app/conversion/webp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to PDF"](conversion/net/images/convert-webp-to-pdf.png)](https://products.groupdocs.app/conversion/webp-to-pdf)