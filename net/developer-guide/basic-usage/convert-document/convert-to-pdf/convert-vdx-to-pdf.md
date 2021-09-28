---
id: convert-vdx-to-pdf
url: conversion/net/convert-vdx-to-pdf
title: Convert VDX to PDF
description: "VDX format represents Microsoft Visio XML Drawing File Format with .vdx extension. Learn how to convert VDX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Any drawing or chart created in Microsoft Visio, but saved in XML format has a VDX extension. A Visio drawing XML file is created in Visio software, which is developed by Microsoft. Microsoft Visio has the capability to generate visual documents that can be used in presentations and documents. The Visio drawing XML file contains the visual objects and metadata details of the visual elements.

To convert from Microsoft Visio XML Drawing File Format (.vdx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VDX file
using (Converter converter = new Converter("sample.vdx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VDX to PDF converter**](https://products.groupdocs.app/conversion/vdx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDX to PDF"](conversion/net/images/convert-vdx-to-pdf.png)](https://products.groupdocs.app/conversion/vdx-to-pdf)