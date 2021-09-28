---
id: convert-eps-to-pdf
url: conversion/net/convert-eps-to-pdf
title: Convert EPS to PDF
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

To convert from Encapsulated PostScript File (.eps) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source EPS file
using (Converter converter = new Converter("sample.eps"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to PDF converter**](https://products.groupdocs.app/conversion/eps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to PDF"](conversion/net/images/convert-eps-to-pdf.png)](https://products.groupdocs.app/conversion/eps-to-pdf)