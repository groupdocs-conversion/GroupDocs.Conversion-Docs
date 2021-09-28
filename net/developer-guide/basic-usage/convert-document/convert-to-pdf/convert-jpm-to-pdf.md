---
id: convert-jpm-to-pdf
url: conversion/net/convert-jpm-to-pdf
title: Convert JPM to PDF
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

To convert from JPEG 2000 Image File (.jpm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JPM file
using (Converter converter = new Converter("sample.jpm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to PDF converter**](https://products.groupdocs.app/conversion/jpm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to PDF"](conversion/net/images/convert-jpm-to-pdf.png)](https://products.groupdocs.app/conversion/jpm-to-pdf)