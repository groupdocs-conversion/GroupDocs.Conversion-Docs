---
id: convert-psd-to-pdf
url: conversion/net/convert-psd-to-pdf
title: Convert PSD to PDF
description: "PSD format represents Adobe Photoshop Document with .psd extension. Learn how to convert PSD to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PSD to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PSD, Photoshop Document, represents Adobe Photoshop's native file format used for graphics designing and development. PSD files may include image layers, adjustment layers, layer masks, annotations, file information, keywords, and other Photoshop-specific elements. Photoshop files have default extension as PSD and have a maximum height and width of 30,000 pixels, and a length limit of two gigabytes.

To convert from Adobe Photoshop Document (.psd) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PSD file
using (Converter converter = new Converter("sample.psd"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PSD to PDF converter**](https://products.groupdocs.app/conversion/psd-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PSD to PDF"](conversion/net/images/convert-psd-to-pdf.png)](https://products.groupdocs.app/conversion/psd-to-pdf)