---
id: eps-to-svg
url: conversion/net/convert/eps-to-svg
title: Convert EPS to SVG
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert EPS to SVG in C#
    appDescription: Convert EPS to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert EPS to SVG in C# 
        description: Quick guide about how to convert EPS to SVG in C# with high performance and accuracy.
        url: conversion/net/convert/eps-to-svg/#steps-to-convert-eps-to-svg-in-c
        steps:
        - name: Load source EPS file 
          text: Create an instance of Converter class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to SVG converter**](https://products.groupdocs.app/conversion/eps-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to SVG"](conversion/net/images/convert-to-svg/convert-eps-to-svg.png)](https://products.groupdocs.app/conversion/eps-to-svg)