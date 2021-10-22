---
id: jp2-to-pdf
url: conversion/net/convert/jp2-to-pdf
title: Convert JP2 to PDF
description: "JP2 format represents JPEG 2000 Core Image File with .jp2 extension. Learn how to convert JP2 to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JP2 to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JP2 to PDF in C#
    appDescription: Convert JP2 to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JP2 to PDF in C# 
        description: Some description
        url: conversion/net/convert/jp2-to-pdf/#steps-to-convert-jp2-to-pdf-in-c
        steps:
        - name: Load source JP2 file 
          text: Create an instance of Converter class and pass source JP2 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

JPEG 2000 (JP2) is an image coding system and state-of-the-art image compression standard. Designed, using wavelet technology JPEG 2000 can code lossless content in any quality at once. Moreover, without any substantial penalty in coding efficiency, JPEG 2000  have the capability to access and decode the same content efficaciously into a variety of other resolutions and qualities. The code streams in JPEG 2000 is significantly scalable having regions of interest that provide the facility for spatial random access. Possessing Up to 16384 diverse components with the dimensions in terapixels, and precision that can be high as 38 bits/sample.

## Steps to convert JP2 to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JP2 file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JP2 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JP2 file
using (var converter = new GroupDocs.Conversion.Converter("sample.jp2"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JP2 to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**JP2 to PDF converter**](https://products.groupdocs.app/conversion/jp2-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JP2 to PDF"](conversion/net/images/convert-to-pdf/convert-jp2-to-pdf.png)](https://products.groupdocs.app/conversion/jp2-to-pdf)