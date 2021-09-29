---
id: convert-dib-to-pdf
url: conversion/net/convert-dib-to-pdf
title: Convert DIB to PDF
description: "DIB format represents Device Independent Bitmap File with .dib extension. Learn how to convert DIB to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DIB to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Device-Independent bitmap (DIB) is a raster image file that is similar in structure to the standard Bitmap files(BMP). It contains a color table that describes the mapping of RGB colors to the pixel values. This enables DIB to represent images on any device. It can be opened with almost all applications that can open a standard BMP file on Windows as well as macOS.

## Steps to convert DIB to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DIB file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DIB file
using (var converter = new GroupDocs.Conversion.Converter("sample.dib"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DIB to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**DIB to PDF converter**](https://products.groupdocs.app/conversion/dib-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DIB to PDF"](conversion/net/images/convert-dib-to-pdf.png)](https://products.groupdocs.app/conversion/dib-to-pdf)