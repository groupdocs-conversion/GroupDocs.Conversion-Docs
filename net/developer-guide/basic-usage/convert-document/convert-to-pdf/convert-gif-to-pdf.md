---
id: convert-gif-to-pdf
url: conversion/net/convert-gif-to-pdf
title: Convert GIF to PDF
description: "GIF format represents Graphical Interchange Format File with .gif extension. Learn how to convert GIF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert GIF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A GIF or Graphical Interchange Format is a type of highly compressed image. Owned by Unisys, GIF uses the LZW compression algorithm that does not degrade the image quality. For each image GIF typically allow up to 8 bits per pixel and up to 256 colors are allowed across the image. In contrast to a JPEG image, which can display up to 16 million colors and fairly touches the limits of the human eye.

To convert from Graphical Interchange Format File (.gif) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source GIF file
using (Converter converter = new Converter("sample.gif"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**GIF to PDF converter**](https://products.groupdocs.app/conversion/gif-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert GIF to PDF"](conversion/net/images/convert-gif-to-pdf.png)](https://products.groupdocs.app/conversion/gif-to-pdf)