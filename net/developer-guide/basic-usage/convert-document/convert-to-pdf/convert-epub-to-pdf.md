---
id: convert-epub-to-pdf
url: conversion/net/convert-epub-to-pdf
title: Convert EPUB to PDF
description: "Convert e-books and digital publication files to PDF in C# easily. Learn this guide that shows EPUB to PDF conversion in a few simple steps."
keywords: Convert EPUB to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EPUB files are e-book format files that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

To convert EPUB to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source EPUB file
using (Converter converter = new Converter("sample.epub"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EPUB to PDF converter**](https://products.groupdocs.app/conversion/epub-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPUB to PDF"](conversion/net/images/convert-epub-to-pdf.png)](https://products.groupdocs.app/conversion/epub-to-pdf)