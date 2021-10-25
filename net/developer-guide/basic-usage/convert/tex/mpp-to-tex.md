---
id: mpp-to-tex
url: conversion/net/convert/mpp-to-tex
title: Convert MPP to TEX
description: "MPP format represents Microsoft Project File with .mpp extension. Learn how to convert MPP to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPP to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MPP to TEX in C#
    appDescription: Convert MPP to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MPP to TEX in C# 
        description: Quick guide about how to convert MPP to TEX in C# with high performance and accuracy.
        url: conversion/net/convert/mpp-to-tex/#steps-to-convert-mpp-to-tex-in-c
        steps:
        - name: Load source MPP file 
          text: Create an instance of Converter class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A file with MPP extension is Microsoft Project data file that stores information related to project management in an integrated manner. It is proprietary file format developed by Microsoft as file format for Microsoft Project (MSP) which is a project management application software. Besides MPP, MSP supports other file formats as well like project XML schema. Several APIs and applications provide the facility to convert MPP file format to others.

## Steps to convert MPP to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPP file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPP file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpp"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPP to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**MPP to TEX converter**](https://products.groupdocs.app/conversion/mpp-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPP to TEX"](conversion/net/images/convert-to-tex/convert-mpp-to-tex.png)](https://products.groupdocs.app/conversion/mpp-to-tex)