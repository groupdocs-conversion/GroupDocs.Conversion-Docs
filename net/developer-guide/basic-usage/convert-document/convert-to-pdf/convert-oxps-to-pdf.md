---
id: convert-oxps-to-pdf
url: conversion/net/convert-oxps-to-pdf
title: Convert OXPS to PDF
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

To convert from XML Paper Specification File (.oxps) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

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