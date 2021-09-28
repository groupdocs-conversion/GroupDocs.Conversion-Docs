---
id: convert-jpf-to-pdf
url: conversion/net/convert-jpf-to-pdf
title: Convert JPF to PDF
description: "JPF format represents JPEG 2000 Image File with .jpf extension. Learn how to convert JPF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPEG 2000 is an image coding system and state-of-the-art image compression standard. It uses wavelet technology to code lossless content in any quality at once. Moreover, without any substantial penalty in coding efficiency, JPEG 2000 has the capability to access and decode the same content efficaciously into a variety of other resolutions and qualities. The code streams in JPEG 2000 are significantly scalable having regions of interest that provide the facility for spatial random access.

To convert from JPEG 2000 Image File (.jpf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JPF file
using (Converter converter = new Converter("sample.jpf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPF to PDF converter**](https://products.groupdocs.app/conversion/jpf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPF to PDF"](conversion/net/images/convert-jpf-to-pdf.png)](https://products.groupdocs.app/conversion/jpf-to-pdf)