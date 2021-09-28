---
id: convert-cdr-to-pdf
url: conversion/net/convert-cdr-to-pdf
title: Convert CDR to PDF
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

To convert from CorelDraw Vector Graphic Drawing (.cdr) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source CDR file
using (Converter converter = new Converter("sample.cdr"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to PDF converter**](https://products.groupdocs.app/conversion/cdr-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to PDF"](conversion/net/images/convert-cdr-to-pdf.png)](https://products.groupdocs.app/conversion/cdr-to-pdf)