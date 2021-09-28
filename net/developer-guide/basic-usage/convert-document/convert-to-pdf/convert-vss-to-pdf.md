---
id: convert-vss-to-pdf
url: conversion/net/convert-vss-to-pdf
title: Convert VSS to PDF
description: "VSS format represents Visio Stencil File with .vss extension. Learn how to convert VSS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSS is stencil files created with Microsoft Visio 2007 and earlier. A relatively new file format is VSSX that was introduced with Microsoft Visio 2013. Stencil files provide drawing objects that can be included in a VSD Visio drawing. Microsoft Visio is used for creating drawing elements such as a collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping, and other similar information.

To convert from Visio Stencil File (.vss) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSS file
using (Converter converter = new Converter("sample.vss"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSS to PDF converter**](https://products.groupdocs.app/conversion/vss-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSS to PDF"](conversion/net/images/convert-vss-to-pdf.png)](https://products.groupdocs.app/conversion/vss-to-pdf)