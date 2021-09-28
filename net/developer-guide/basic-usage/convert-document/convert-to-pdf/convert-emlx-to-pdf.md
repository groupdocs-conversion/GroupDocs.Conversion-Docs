---
id: convert-emlx-to-pdf
url: conversion/net/convert-emlx-to-pdf
title: Convert EMLX to PDF
description: "EMLX format represents Apple Mail Message with .emlx extension. Learn how to convert EMLX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMLX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The EMLX file format is implemented and developed by Apple. The Apple Mail application uses the EMLX file format for exporting the emails. There are other applications as well such as GroupDocs.Conversion App that can open the EMLX files and convert these to other file formats.

To convert from Apple Mail Message (.emlx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source EMLX file
using (Converter converter = new Converter("sample.emlx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EMLX to PDF converter**](https://products.groupdocs.app/conversion/emlx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMLX to PDF"](conversion/net/images/convert-emlx-to-pdf.png)](https://products.groupdocs.app/conversion/emlx-to-pdf)