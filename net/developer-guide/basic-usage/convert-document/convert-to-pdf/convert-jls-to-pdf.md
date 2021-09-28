---
id: convert-jls-to-pdf
url: conversion/net/convert-jls-to-pdf
title: Convert JLS to PDF
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

To convert from JPEG Lossless Image File (.jls) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JLS file
using (Converter converter = new Converter("sample.jls"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to PDF converter**](https://products.groupdocs.app/conversion/jls-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to PDF"](conversion/net/images/convert-jls-to-pdf.png)](https://products.groupdocs.app/conversion/jls-to-pdf)