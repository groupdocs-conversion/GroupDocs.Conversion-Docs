---
id: convert-ps-to-pdf
url: conversion/net/convert-ps-to-pdf
title: Convert PS to PDF
description: "PS format represents PostScript (PS) with .ps extension. Learn how to convert PS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straightforward interpretation.

To convert from PostScript (PS) (.ps) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PS file
using (Converter converter = new Converter("sample.ps"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PS to PDF converter**](https://products.groupdocs.app/conversion/ps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PS to PDF"](conversion/net/images/convert-ps-to-pdf.png)](https://products.groupdocs.app/conversion/ps-to-pdf)