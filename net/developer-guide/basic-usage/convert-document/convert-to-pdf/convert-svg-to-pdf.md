---
id: convert-svg-to-pdf
url: conversion/net/convert-svg-to-pdf
title: Convert SVG to PDF
description: "Groupdocs.Conversion for .NET provides a convert SVG to PDF feature. Review this article to learn more about SVG format transformations and simple C# code snippet."
keywords: Convert SVG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An SVG file is a Scalar Vector Graphics file that uses XML based text format for describing the appearance of an image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text-based description of such files makes them independent of resolution. It is one of the most used formats for building a website and print graphics in order to achieve scalability. The format can only be used for two-dimensional graphics though. SVG files can be viewed/opened in almost all modern browsers including Chrome, Internet Explorer, Firefox, and Safari.

To convert SVG to PDF file in C# just call `Convert` method like shown below:

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