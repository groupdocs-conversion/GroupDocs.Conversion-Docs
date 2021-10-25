---
id: webp-to-pptx
url: conversion/net/convert/webp-to-pptx
title: Convert WEBP to PPTX
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert WEBP to PPTX in C#
    appDescription: Convert WEBP to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert WEBP to PPTX in C# 
        description: Quick guide about how to convert WEBP to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/webp-to-pptx/#steps-to-convert-webp-to-pptx-in-c
        steps:
        - name: Load source WEBP file 
          text: Create an instance of Converter class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPTX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to PPTX converter**](https://products.groupdocs.app/conversion/webp-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to PPTX"](conversion/net/images/convert-to-pptx/convert-webp-to-pptx.png)](https://products.groupdocs.app/conversion/webp-to-pptx)