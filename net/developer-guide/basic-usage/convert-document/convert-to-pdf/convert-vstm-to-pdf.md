---
id: convert-vstm-to-pdf
url: conversion/net/convert-vstm-to-pdf
title: Convert VSTM to PDF
description: "VSTM format represents Visio Macro-Enabled Drawing Template with .vstm extension. Learn how to convert VSTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSTM extension are template files created with Microsoft Visio that support macros. Unlike VSDX files, files created from VSTM templates can run macros that are developed in Visual Basic for Applications (VBA) code. A template file can be created in order to provide basic settings of the document that can be utilized to generate further documents with these settings.

To convert from Visio Macro-Enabled Drawing Template (.vstm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSTM file
using (Converter converter = new Converter("sample.vstm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTM to PDF converter**](https://products.groupdocs.app/conversion/vstm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTM to PDF"](conversion/net/images/convert-vstm-to-pdf.png)](https://products.groupdocs.app/conversion/vstm-to-pdf)