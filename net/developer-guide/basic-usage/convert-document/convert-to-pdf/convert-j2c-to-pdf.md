---
id: convert-j2c-to-pdf
url: conversion/net/convert-j2c-to-pdf
title: Convert J2C to PDF
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

To convert from JPEG 2000 Image File (.j2c) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source J2C file
using (Converter converter = new Converter("sample.j2c"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to PDF converter**](https://products.groupdocs.app/conversion/j2c-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to PDF"](conversion/net/images/convert-j2c-to-pdf.png)](https://products.groupdocs.app/conversion/j2c-to-pdf)