---
id: ppsm-to-svg
url: conversion/net/convert/ppsm-to-svg
title: Convert PPSM to SVG
description: "PPSM format represents Microsoft PowerPoint Slide Show with .ppsm extension. Learn how to convert PPSM to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSM to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PPSM to SVG in C#
    appDescription: Convert PPSM to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PPSM to SVG in C# 
        description: Some description
        url: conversion/net/convert/ppsm-to-svg/#steps-to-convert-ppsm-to-svg-in-c
        steps:
        - name: Load source PPSM file 
          text: Create an instance of Converter class and pass source PPSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is PPTM which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as slide show, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening it in PowerPoint.

## Steps to convert PPSM to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPSM file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppsm"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPSM to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSM to SVG converter**](https://products.groupdocs.app/conversion/ppsm-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSM to SVG"](conversion/net/images/convert-to-svg/convert-ppsm-to-svg.png)](https://products.groupdocs.app/conversion/ppsm-to-svg)