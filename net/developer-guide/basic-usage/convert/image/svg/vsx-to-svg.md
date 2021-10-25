---
id: vsx-to-svg
url: conversion/net/convert/vsx-to-svg
title: Convert VSX to SVG
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSX to SVG in C#
    appDescription: Convert VSX to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSX to SVG in C# 
        description: Quick guide about how to convert VSX to SVG in C# with high performance and accuracy.
        url: conversion/net/convert/vsx-to-svg/#steps-to-convert-vsx-to-svg-in-c
        steps:
        - name: Load source VSX file 
          text: Create an instance of Converter class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

## Steps to convert VSX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to SVG converter**](https://products.groupdocs.app/conversion/vsx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to SVG"](conversion/net/images/convert-to-svg/convert-vsx-to-svg.png)](https://products.groupdocs.app/conversion/vsx-to-svg)