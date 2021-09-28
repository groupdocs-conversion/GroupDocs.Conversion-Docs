---
id: convert-svg-to-pdf
url: conversion/net/convert-svg-to-pdf
title: Convert SVG to PDF
description: "SVG format represents Scalable Vector Graphics File with .svg extension. Learn how to convert SVG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

SVG files are Scalable Vector Graphics Files that use XML based text format for describing the appearance of image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text based description of such files make them independent of resolution. It is one of the mostly used format for building website and print graphics in order to achieve scalability.

To convert from Scalable Vector Graphics File (.svg) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source SVG file
using (Converter converter = new Converter("sample.svg"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**SVG to PDF converter**](https://products.groupdocs.app/conversion/svg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVG to PDF"](conversion/net/images/convert-svg-to-pdf.png)](https://products.groupdocs.app/conversion/svg-to-pdf)