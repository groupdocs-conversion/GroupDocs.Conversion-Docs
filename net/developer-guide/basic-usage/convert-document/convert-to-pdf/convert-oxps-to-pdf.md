---
id: convert-oxps-to-pdf
url: conversion/net/convert-oxps-to-pdf
title: Convert OXPS to PDF
description: "Learn our guide that shows how to convert OXPS to PDF file in C# language. Use GroupDocs.Conversion for .NET to transform page description language files to PDF documents or other file types."
keywords: Convert OXPS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The file format OXPS is known as Open XML Paper Specification. It’s a page description language and document format. Microsoft is the developer of this format. OXPS file format is very much familiar to these PDF files. The setup of the OXPS file is the same as an XPS format. The only difference is the description of OXPS as an open format. The .oxps file extension is the most current version of the XPS file format originated by Microsoft and Ecma International. If we talk about the specification, the OXPS and XPS files are used to publish, share, and allocate fixed-layout documents. As a substitute to PDFs, the OXPS file format can store text and multimedia data, with arranging features and printing layout characteristics.

To convert OXPS to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source OXPS file
using (Converter converter = new Converter("sample.oxps"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to PDF converter**](https://products.groupdocs.app/conversion/oxps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to PDF"](conversion/net/images/convert-oxps-to-pdf.png)](https://products.groupdocs.app/conversion/oxps-to-pdf)