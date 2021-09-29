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

## Steps to convert VCF to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VCF file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VCF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VCF file
using (var converter = new GroupDocs.Conversion.Converter("sample.vcf"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VCF to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**VCF to PDF converter**](https://products.groupdocs.app/conversion/vcf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VCF to PDF"](conversion/net/images/convert-vcf-to-pdf.png)](https://products.groupdocs.app/conversion/vcf-to-pdf)