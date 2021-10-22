---
id: emlx-to-svg
url: conversion/net/convert/emlx-to-svg
title: Convert EMLX to SVG
description: "EMLX format represents Apple Mail Message with .emlx extension. Learn how to convert EMLX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMLX to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert EMLX to SVG in C#
    appDescription: Convert EMLX to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert EMLX to SVG in C# 
        description: Some description
        url: conversion/net/convert/emlx-to-svg/#steps-to-convert-emlx-to-svg-in-c
        steps:
        - name: Load source EMLX file 
          text: Create an instance of Converter class and pass source EMLX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

The EMLX file format is implemented and developed by Apple. The Apple Mail application uses the EMLX file format for exporting the emails. There are other applications as well such as GroupDocs.Conversion App that can open the EMLX files and convert these to other file formats.

## Steps to convert EMLX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMLX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMLX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMLX file
using (var converter = new GroupDocs.Conversion.Converter("sample.emlx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMLX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMLX to SVG converter**](https://products.groupdocs.app/conversion/emlx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMLX to SVG"](conversion/net/images/convert-to-svg/convert-emlx-to-svg.png)](https://products.groupdocs.app/conversion/emlx-to-svg)