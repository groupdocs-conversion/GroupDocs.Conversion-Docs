---
id: convert-vst-to-pdf
url: conversion/net/convert-vst-to-pdf
title: Convert VST to PDF
description: "VST format represents Visio Drawing Template with .vst extension. Learn how to convert VST to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VST to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VST extension are vector image files created with Microsoft Visio and act as templates for creating further files. These template files are in binary file format and contain the default layout and settings that are utilized for the creation of new Visio drawings. When a VST file is opened in Microsoft Visio, it contains the existing settings to continue working with the document. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

To convert from Visio Drawing Template (.vst) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VST file
using (Converter converter = new Converter("sample.vst"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VST to PDF converter**](https://products.groupdocs.app/conversion/vst-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VST to PDF"](conversion/net/images/convert-vst-to-pdf.png)](https://products.groupdocs.app/conversion/vst-to-pdf)