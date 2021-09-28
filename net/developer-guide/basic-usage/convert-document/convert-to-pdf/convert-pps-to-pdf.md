---
id: convert-pps-to-pdf
url: conversion/net/convert-pps-to-pdf
title: Convert PPS to PDF
description: "PPS format represents Microsoft PowerPoint Slide Show with .pps extension. Learn how to convert PPS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PPS, PowerPoint Slide Show, files are created using Microsoft PowerPoint for Slide Show purpose. PPS file reading and creation is supported by Microsoft PowerPoint 97-2003. The more latest version of this file format is PPSX which is based on Office OpenXML standards. PPS files can still be read by latest versions of Microsoft PowerPoint, but newly created files can only be saved in PPSX file format. When a PPS file is shared with another user and opened, it starts as Powerpoint show unlike PPT file which opens in editable mode. 

To convert from Microsoft PowerPoint Slide Show (.pps) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PPS file
using (Converter converter = new Converter("sample.pps"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPS to PDF converter**](https://products.groupdocs.app/conversion/pps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPS to PDF"](conversion/net/images/convert-pps-to-pdf.png)](https://products.groupdocs.app/conversion/pps-to-pdf)