---
id: mobi-to-pdf
url: conversion/net/convert/mobi-to-pdf
title: Convert MOBI to PDF
description: "MOBI format represents Mobipocket eBook with .mobi extension. Learn how to convert MOBI to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MOBI to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MOBI to PDF in C#
    appDescription: Convert MOBI to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MOBI to PDF in C# 
        description: Some description
        url: conversion/net/convert/mobi-to-pdf/#steps-to-convert-mobi-to-pdf-in-c
        steps:
        - name: Load source MOBI file 
          text: Create an instance of Converter class and pass source MOBI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

The MOBI file format is one of the most widely used ebook file formats. The format is an enhancement to the old OEB (Open Ebook Format) format and was used as the proprietary format for Mobipocket Reader. Like EPUB, it is supported by almost all modern e-readers specifically by mobile devices with low bandwidth. The format can be converted to several other formats such as PDF, EPUB, and several other formats using publicly available software applications such as the Kindle app.

## Steps to convert MOBI to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MOBI file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MOBI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MOBI file
using (var converter = new GroupDocs.Conversion.Converter("sample.mobi"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MOBI to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**MOBI to PDF converter**](https://products.groupdocs.app/conversion/mobi-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MOBI to PDF"](conversion/net/images/convert-to-pdf/convert-mobi-to-pdf.png)](https://products.groupdocs.app/conversion/mobi-to-pdf)