---
id: vssx-to-svg
url: conversion/net/convert/vssx-to-svg
title: Convert VSSX to SVG
description: "VSSX format represents Visio Stencil File Format with .vssx extension. Learn how to convert VSSX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSX to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSSX to SVG in C#
    appDescription: Convert VSSX to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSSX to SVG in C# 
        description: Some description
        url: conversion/net/convert/vssx-to-svg/#steps-to-convert-vssx-to-svg-in-c
        steps:
        - name: Load source VSSX file 
          text: Create an instance of Converter class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

## Steps to convert VSSX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vssx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSSX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSX to SVG converter**](https://products.groupdocs.app/conversion/vssx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSX to SVG"](conversion/net/images/convert-to-svg/convert-vssx-to-svg.png)](https://products.groupdocs.app/conversion/vssx-to-svg)