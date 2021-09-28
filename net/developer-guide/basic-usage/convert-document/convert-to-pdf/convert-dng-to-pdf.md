---
id: convert-dng-to-pdf
url: conversion/net/convert-dng-to-pdf
title: Convert DNG to PDF
description: "DNG format represents Digital Camera Image Format with .dng extension. Learn how to convert DNG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DNG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DNG is a digital camera image format used for the storage of raw files. It has been developed by Adobe in September 2004. It was basically developed for digital photography. DNG is an extension of TIFF/EP standard format and uses metadata significantly. In order to manipulate raw data from digital cameras with ease of flexibility and artistic control, photographers opt camera raw files.

To convert from Digital Camera Image Format (.dng) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DNG file
using (Converter converter = new Converter("sample.dng"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DNG to PDF converter**](https://products.groupdocs.app/conversion/dng-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DNG to PDF"](conversion/net/images/convert-dng-to-pdf.png)](https://products.groupdocs.app/conversion/dng-to-pdf)