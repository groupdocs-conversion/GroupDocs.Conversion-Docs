---
id: convert-j2k-to-pdf
url: conversion/net/convert-j2k-to-pdf
title: Convert J2K to PDF
description: "J2K format represents JPEG 2000 Image with .j2k extension. Learn how to convert J2K to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2K to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2K file is an image that is compressed using the wavelet compression instead of DCT compression.

To convert from JPEG 2000 Image (.j2k) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source J2K file
using (Converter converter = new Converter("sample.j2k"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**J2K to PDF converter**](https://products.groupdocs.app/conversion/j2k-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2K to PDF"](conversion/net/images/convert-j2k-to-pdf.png)](https://products.groupdocs.app/conversion/j2k-to-pdf)