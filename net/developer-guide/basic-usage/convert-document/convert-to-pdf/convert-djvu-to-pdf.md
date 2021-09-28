---
id: convert-djvu-to-pdf
url: conversion/net/convert-djvu-to-pdf
title: Convert DJVU to PDF
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

To convert from Graphics File format (.djvu) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DJVU file
using (Converter converter = new Converter("sample.djvu"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to PDF converter**](https://products.groupdocs.app/conversion/djvu-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to PDF"](conversion/net/images/convert-djvu-to-pdf.png)](https://products.groupdocs.app/conversion/djvu-to-pdf)