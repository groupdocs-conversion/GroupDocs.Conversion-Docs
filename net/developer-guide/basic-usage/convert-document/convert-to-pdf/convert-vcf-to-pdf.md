---
id: convert-vcf-to-pdf
url: conversion/net/convert-vcf-to-pdf
title: Convert VCF to PDF
description: "Virtual Card Format or vCard is a digital file format for storing contact information .vcf extension. You may easily convert VCF files to PDF format in C# with Groupdocs.Conversion for .NET."
keywords: Convert VCF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VCF (Virtual Card Format) or vCard is a digital file format for storing contact information. The format is widely used for data interchange among popular information exchange applications. Most operating systems such as Windows and MacOS come with default applications to create and open these files. A single VCF file can contain contact information for one or multiple contacts. A VCF file usually contains information such as contact’s name, address, phone number, email, birthday, photographs and audio in addition to a number of other fields. Being supported by email clients and services, there is no loss of data during the transfer of contacts via using the vCard format. The media type for VCF file format is text/vcard.

To convert VCF to PDF file in C# just call `Convert` method like shown below:

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