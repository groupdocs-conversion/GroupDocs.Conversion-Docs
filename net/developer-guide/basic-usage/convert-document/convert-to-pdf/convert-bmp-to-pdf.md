---
id: convert-bmp-to-pdf
url: conversion/net/convert-bmp-to-pdf
title: Convert BMP to PDF
description: "This guide explains how to convert BMP image to PDF document using C# with help of GroupDocs.Conversion for .NET."
keywords: Convert BMP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

BMP files are  used to store bitmap digital images. Which are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency allows to open such files on different platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images in both monochrome as well as color format with various colour depths.

To convert BMP to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source BMP file
using (Converter converter = new Converter("sample.bmp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**BMP to PDF converter**](https://products.groupdocs.app/conversion/bmp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert BMP to PDF"](conversion/net/images/convert-bmp-to-pdf.png)](https://products.groupdocs.app/conversion/bmp-to-pdf)