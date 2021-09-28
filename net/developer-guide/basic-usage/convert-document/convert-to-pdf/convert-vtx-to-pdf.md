---
id: convert-vtx-to-pdf
url: conversion/net/convert-vtx-to-pdf
title: Convert VTX to PDF
description: "VTX format represents Microsoft Visio Drawing Template with .vtx extension. Learn how to convert VTX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VTX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

To convert from Microsoft Visio Drawing Template (.vtx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VTX file
using (Converter converter = new Converter("sample.vtx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VTX to PDF converter**](https://products.groupdocs.app/conversion/vtx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VTX to PDF"](conversion/net/images/convert-vtx-to-pdf.png)](https://products.groupdocs.app/conversion/vtx-to-pdf)