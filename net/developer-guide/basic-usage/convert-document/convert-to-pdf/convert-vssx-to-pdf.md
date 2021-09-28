---
id: convert-vssx-to-pdf
url: conversion/net/convert-vssx-to-pdf
title: Convert VSSX to PDF
description: "VSSX format represents Visio Stencil File Format with .vssx extension. Learn how to convert VSSX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

To convert from Visio Stencil File Format (.vssx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSSX file
using (Converter converter = new Converter("sample.vssx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSX to PDF converter**](https://products.groupdocs.app/conversion/vssx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSX to PDF"](conversion/net/images/convert-vssx-to-pdf.png)](https://products.groupdocs.app/conversion/vssx-to-pdf)