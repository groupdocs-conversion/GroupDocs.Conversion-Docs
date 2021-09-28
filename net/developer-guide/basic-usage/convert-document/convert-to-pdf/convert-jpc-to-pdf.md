---
id: convert-jpc-to-pdf
url: conversion/net/convert-jpc-to-pdf
title: Convert JPC to PDF
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

To convert from JPEG 2000 Image File (.jpc) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JPC file
using (Converter converter = new Converter("sample.jpc"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to PDF converter**](https://products.groupdocs.app/conversion/jpc-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to PDF"](conversion/net/images/convert-jpc-to-pdf.png)](https://products.groupdocs.app/conversion/jpc-to-pdf)