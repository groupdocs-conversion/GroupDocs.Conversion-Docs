---
id: convert-vsdm-to-pdf
url: conversion/net/convert-vsdm-to-pdf
title: Convert VSDM to PDF
description: "VSDM format represents Visio Macro-Enabled Drawing with .vsdm extension. Learn how to convert VSDM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSDM extension are drawing files created with Microsoft Visio application that supports macros. VSDM files are OPC/XML drawings that are similar to VSDX but also provide the capability to run macros when the file is opened. Macros are user-defined actions/steps that are developed in Visual Basic for Applications (VBA) and can be used to perform repetitive tasks.

To convert from Visio Macro-Enabled Drawing (.vsdm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSDM file
using (Converter converter = new Converter("sample.vsdm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDM to PDF converter**](https://products.groupdocs.app/conversion/vsdm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDM to PDF"](conversion/net/images/convert-vsdm-to-pdf.png)](https://products.groupdocs.app/conversion/vsdm-to-pdf)