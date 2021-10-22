---
id: eps-to-pdf
url: conversion/net/convert/eps-to-pdf
title: Convert EPS to PDF
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert EPS to PDF in C#
    appDescription: Convert EPS to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert EPS to PDF in C# 
        description: Some description
        url: conversion/net/convert/eps-to-pdf/#steps-to-convert-eps-to-pdf-in-c
        steps:
        - name: Load source EPS file 
          text: Create an instance of Converter class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to PDF converter**](https://products.groupdocs.app/conversion/eps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to PDF"](conversion/net/images/convert-to-pdf/convert-eps-to-pdf.png)](https://products.groupdocs.app/conversion/eps-to-pdf)