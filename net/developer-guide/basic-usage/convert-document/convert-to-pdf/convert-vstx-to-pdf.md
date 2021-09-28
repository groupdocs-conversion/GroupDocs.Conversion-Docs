---
id: convert-vstx-to-pdf
url: conversion/net/convert-vstx-to-pdf
title: Convert VSTX to PDF
description: "VSTX format represents Microsoft Visio File Format with .vstx extension. Learn how to convert VSTX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSTX extensions are drawing template files created with Microsoft Visio 2013 and above. These VSTX files provide a starting point for creating Visio drawings, saved as VSDX files, with default layout and settings. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

To convert from Microsoft Visio File Format (.vstx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSTX file
using (Converter converter = new Converter("sample.vstx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTX to PDF converter**](https://products.groupdocs.app/conversion/vstx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTX to PDF"](conversion/net/images/convert-vstx-to-pdf.png)](https://products.groupdocs.app/conversion/vstx-to-pdf)