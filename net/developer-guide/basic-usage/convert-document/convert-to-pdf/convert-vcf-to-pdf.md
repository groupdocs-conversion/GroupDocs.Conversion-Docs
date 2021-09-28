---
id: convert-vcf-to-pdf
url: conversion/net/convert-vcf-to-pdf
title: Convert VCF to PDF
description: "VCF format represents vCard File with .vcf extension. Learn how to convert VCF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VCF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VCF (Virtual Card Format) or vCard is a digital file format for storing contact information. The format is widely used for data interchange among popular information exchange applications. Most operating systems such as Windows and macOS come with default applications to create and open these files. A single VCF file can contain contact information for one or multiple contacts.

To convert from vCard File (.vcf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VCF file
using (Converter converter = new Converter("sample.vcf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VCF to PDF converter**](https://products.groupdocs.app/conversion/vcf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VCF to PDF"](conversion/net/images/convert-vcf-to-pdf.png)](https://products.groupdocs.app/conversion/vcf-to-pdf)