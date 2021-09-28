---
id: convert-vsd-to-pdf
url: conversion/net/convert-vsd-to-pdf
title: Convert VSD to PDF
description: "VSD format represents Visio Drawing File Format with .vsd extension. Learn how to convert VSD to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSD to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSD files are drawings created with Microsoft Visio application to represent variety of graphical objects and the interconnection between these. Such drawings can contain visual objects such as visual objects, flow charts, UML diagram, information flow, organizational charts, software diagrams, network layout, database models, objects mapping and other similar information. Microsoft Visio offers the capability to convert Visio files to a number of different file formats including PNG, BMP, PDF and others.

To convert from Visio Drawing File Format (.vsd) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSD file
using (Converter converter = new Converter("sample.vsd"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSD to PDF converter**](https://products.groupdocs.app/conversion/vsd-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSD to PDF"](conversion/net/images/convert-vsd-to-pdf.png)](https://products.groupdocs.app/conversion/vsd-to-pdf)