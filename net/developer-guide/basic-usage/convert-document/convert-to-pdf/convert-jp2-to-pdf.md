---
id: convert-jp2-to-pdf
url: conversion/net/convert-jp2-to-pdf
title: Convert JP2 to PDF
description: "JP2 format represents JPEG 2000 Core Image File with .jp2 extension. Learn how to convert JP2 to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JP2 to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPEG 2000 (JP2) is an image coding system and state-of-the-art image compression standard. Designed, using wavelet technology JPEG 2000 can code lossless content in any quality at once. Moreover, without any substantial penalty in coding efficiency, JPEG 2000  have the capability to access and decode the same content efficaciously into a variety of other resolutions and qualities. The code streams in JPEG 2000 is significantly scalable having regions of interest that provide the facility for spatial random access. Possessing Up to 16384 diverse components with the dimensions in terapixels, and precision that can be high as 38 bits/sample.

To convert from JPEG 2000 Core Image File (.jp2) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JP2 file
using (Converter converter = new Converter("sample.jp2"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JP2 to PDF converter**](https://products.groupdocs.app/conversion/jp2-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JP2 to PDF"](conversion/net/images/convert-jp2-to-pdf.png)](https://products.groupdocs.app/conversion/jp2-to-pdf)