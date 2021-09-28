---
id: convert-odp-to-pdf
url: conversion/net/convert-odp-to-pdf
title: Convert ODP to PDF
description: "ODP format represents OpenDocument Presentation File Format with .odp extension. Learn how to convert ODP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

To convert from OpenDocument Presentation File Format (.odp) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source ODP file
using (Converter converter = new Converter("sample.odp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**ODP to PDF converter**](https://products.groupdocs.app/conversion/odp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODP to PDF"](conversion/net/images/convert-odp-to-pdf.png)](https://products.groupdocs.app/conversion/odp-to-pdf)