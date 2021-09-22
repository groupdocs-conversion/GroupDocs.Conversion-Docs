---
id: convert-pptx-to-pdf
url: conversion/net/convert-pptx-to-pdf
title: Convert PPTX to PDF
description: "Microsoft PowerPoint PPTX presentation can be converted to PDF document using C# language. Check a simple code snippet to know how to convert PPTX to PDF using Groupdocs.Conversion for .NET library."
keywords: Convert PPTX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media. These slides are presented to audience in the form of slideshows with custom presentation settings.

To convert PPTX to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source PPTX file
using (Converter converter = new Converter("sample.pptx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTX to PDF converter**](https://products.groupdocs.app/conversion/pptx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTX to PDF"](conversion/net/images/convert-pptx-to-pdf.png)](https://products.groupdocs.app/conversion/pptx-to-pdf)