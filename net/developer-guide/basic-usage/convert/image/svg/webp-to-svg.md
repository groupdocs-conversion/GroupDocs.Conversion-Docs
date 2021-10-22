---
id: webp-to-svg
url: conversion/net/convert/webp-to-svg
title: Convert WEBP to SVG
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert WEBP to SVG in C#
    appDescription: Convert WEBP to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert WEBP to SVG in C# 
        description: Some description
        url: conversion/net/convert/webp-to-svg/#steps-to-convert-webp-to-svg-in-c
        steps:
        - name: Load source WEBP file 
          text: Create an instance of Converter class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to SVG and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to SVG converter**](https://products.groupdocs.app/conversion/webp-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to SVG"](conversion/net/images/convert-to-svg/convert-webp-to-svg.png)](https://products.groupdocs.app/conversion/webp-to-svg)