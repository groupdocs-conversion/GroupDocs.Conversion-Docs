---
id: convert-plt-to-pdf
url: conversion/net/convert-plt-to-pdf
title: Convert PLT to PDF
description: "PLT format represents PLT (HPGL) with .plt extension. Learn how to convert PLT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PLT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An HPGL(Hewlett-Packard Graphics Language) file contains an instruction set for plotter control, developed by Hewlett-Packard. Hewlett-Packard plotters use this file to draw and print vector and raster content on the paper.

To convert from PLT (HPGL) (.plt) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PLT file
using (Converter converter = new Converter("sample.plt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PLT to PDF converter**](https://products.groupdocs.app/conversion/plt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PLT to PDF"](conversion/net/images/convert-plt-to-pdf.png)](https://products.groupdocs.app/conversion/plt-to-pdf)