---
id: dib-to-docx
url: conversion/net/convert/dib-to-docx
title: Convert DIB to DOCX
description: "DIB format represents Device Independent Bitmap File with .dib extension. Learn how to convert DIB to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DIB to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DIB to DOCX in C#
    appDescription: Convert DIB to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DIB to DOCX in C# 
        description: Quick guide about how to convert DIB to DOCX in C# with high performance and accuracy.
        url: conversion/net/convert/dib-to-docx/#steps-to-convert-dib-to-docx-in-c
        steps:
        - name: Load source DIB file 
          text: Create an instance of Converter class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A Device-Independent bitmap (DIB) is a raster image file that is similar in structure to the standard Bitmap files(BMP). It contains a color table that describes the mapping of RGB colors to the pixel values. This enables DIB to represent images on any device. It can be opened with almost all applications that can open a standard BMP file on Windows as well as macOS.

## Steps to convert DIB to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DIB file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DIB file
using (var converter = new GroupDocs.Conversion.Converter("sample.dib"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DIB to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DIB to DOCX converter**](https://products.groupdocs.app/conversion/dib-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DIB to DOCX"](conversion/net/images/convert-to-docx/convert-dib-to-docx.png)](https://products.groupdocs.app/conversion/dib-to-docx)