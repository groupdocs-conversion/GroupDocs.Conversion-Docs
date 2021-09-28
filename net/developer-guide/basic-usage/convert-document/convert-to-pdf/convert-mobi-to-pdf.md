---
id: convert-mobi-to-pdf
url: conversion/net/convert-mobi-to-pdf
title: Convert MOBI to PDF
description: "MOBI format represents Mobipocket eBook with .mobi extension. Learn how to convert MOBI to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MOBI to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The MOBI file format is one of the most widely used ebook file formats. The format is an enhancement to the old OEB (Open Ebook Format) format and was used as the proprietary format for Mobipocket Reader. Like EPUB, it is supported by almost all modern e-readers specifically by mobile devices with low bandwidth. The format can be converted to several other formats such as PDF, EPUB, and several other formats using publicly available software applications such as the Kindle app.

To convert from Mobipocket eBook (.mobi) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MOBI file
using (Converter converter = new Converter("sample.mobi"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MOBI to PDF converter**](https://products.groupdocs.app/conversion/mobi-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MOBI to PDF"](conversion/net/images/convert-mobi-to-pdf.png)](https://products.groupdocs.app/conversion/mobi-to-pdf)