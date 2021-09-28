---
id: convert-svgz-to-pdf
url: conversion/net/convert-svgz-to-pdf
title: Convert SVGZ to PDF
description: "SVGZ format represents Compressed Scalable Vector Graphics File with .svgz extension. Learn how to convert SVGZ to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVGZ to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .svgz extension is a compressed version of Scalable Vector Graphics (.SVG) file. It is compressed with gzip compression and contains data in XML format. SVGZ files support transparency, gradients, animations, and filters. SVGZ files are smaller in size as compared to the default SVG files and this reduced file size helps transfer the graphics files.

To convert from Compressed Scalable Vector Graphics File (.svgz) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source SVGZ file
using (Converter converter = new Converter("sample.svgz"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**SVGZ to PDF converter**](https://products.groupdocs.app/conversion/svgz-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVGZ to PDF"](conversion/net/images/convert-svgz-to-pdf.png)](https://products.groupdocs.app/conversion/svgz-to-pdf)