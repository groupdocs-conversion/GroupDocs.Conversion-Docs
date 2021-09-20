---
id: convert-vsdx-to-pdf
url: conversion/net/convert-vsdx-to-pdf
title: Convert VSDX to PDF
description: "Groupdocs.Conversion for .NET provides an intuitive and straightforward way to convert Microsoft Visio drawings with .vsdx extension to PDF files. Check this article to perform VSDX to PDF conversion in C#."
keywords: Convert VSDX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .vsdx extension represent Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server. Visio files are used to create drawings that contain visual objects, flow charts, UML diagram, information flow, organizational charts, software diagrams, network layout, database models, objects mapping and other similar information. Files generated using Visio can also be exported to different file formats such as PNG, BMP, PDF and others.

To convert VSDX to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source VSDX file
using (Converter converter = new Converter("sample.vsdx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to PDF converter**](https://products.groupdocs.app/conversion/vsdx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to PDF"](conversion/net/images/convert-vsdx-to-pdf.png)](https://products.groupdocs.app/conversion/vsdx-to-pdf)