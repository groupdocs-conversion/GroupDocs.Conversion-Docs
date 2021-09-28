---
id: convert-emz-to-pdf
url: conversion/net/convert-emz-to-pdf
title: Convert EMZ to PDF
description: "EMZ format represents Enhanced Windows Metafile Compressed with .emz extension. Learn how to convert EMZ to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMZ to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .emz extension is a compressed container of Enhanced Metafile (.emf file). It follows GZIP compression algorithm and takes less storage space due to compression. The small file size makes it more easy to transfer EMZ files over the network.

To convert from Enhanced Windows Metafile Compressed (.emz) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source EMZ file
using (Converter converter = new Converter("sample.emz"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to PDF converter**](https://products.groupdocs.app/conversion/emz-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to PDF"](conversion/net/images/convert-emz-to-pdf.png)](https://products.groupdocs.app/conversion/emz-to-pdf)