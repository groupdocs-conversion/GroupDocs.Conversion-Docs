---
id: jpf-to-tex
url: conversion/net/convert/jpf-to-tex
title: Convert JPF to TEX
description: "JPF format represents JPEG 2000 Image File with .jpf extension. Learn how to convert JPF to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPF to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JPF to TEX in C#
    appDescription: Convert JPF to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JPF to TEX in C# 
        description: Some description
        url: conversion/net/convert/jpf-to-tex/#steps-to-convert-jpf-to-tex-in-c
        steps:
        - name: Load source JPF file 
          text: Create an instance of Converter class and pass source JPF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TEX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

JPEG 2000 is an image coding system and state-of-the-art image compression standard. It uses wavelet technology to code lossless content in any quality at once. Moreover, without any substantial penalty in coding efficiency, JPEG 2000 has the capability to access and decode the same content efficaciously into a variety of other resolutions and qualities. The code streams in JPEG 2000 are significantly scalable having regions of interest that provide the facility for spatial random access.

## Steps to convert JPF to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPF file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPF file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpf"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPF to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPF to TEX converter**](https://products.groupdocs.app/conversion/jpf-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPF to TEX"](conversion/net/images/convert-to-tex/convert-jpf-to-tex.png)](https://products.groupdocs.app/conversion/jpf-to-tex)