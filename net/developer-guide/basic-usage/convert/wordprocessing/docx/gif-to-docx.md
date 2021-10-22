---
id: gif-to-docx
url: conversion/net/convert/gif-to-docx
title: Convert GIF to DOCX
description: "GIF format represents Graphical Interchange Format File with .gif extension. Learn how to convert GIF to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert GIF to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert GIF to DOCX in C#
    appDescription: Convert GIF to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert GIF to DOCX in C# 
        description: Some description
        url: conversion/net/convert/gif-to-docx/#steps-to-convert-gif-to-docx-in-c
        steps:
        - name: Load source GIF file 
          text: Create an instance of Converter class and pass source GIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A GIF or Graphical Interchange Format is a type of highly compressed image. Owned by Unisys, GIF uses the LZW compression algorithm that does not degrade the image quality. For each image GIF typically allow up to 8 bits per pixel and up to 256 colors are allowed across the image. In contrast to a JPEG image, which can display up to 16 million colors and fairly touches the limits of the human eye.

## Steps to convert GIF to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the GIF file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source GIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source GIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.gif"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### GIF to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**GIF to DOCX converter**](https://products.groupdocs.app/conversion/gif-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert GIF to DOCX"](conversion/net/images/convert-to-docx/convert-gif-to-docx.png)](https://products.groupdocs.app/conversion/gif-to-docx)