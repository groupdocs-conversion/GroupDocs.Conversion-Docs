---
id: vdw-to-ppt
url: conversion/net/convert/vdw-to-ppt
title: Convert VDW to PPT
description: "VDW format represents Visio Web Drawing with .vdw extension. Learn how to convert VDW to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDW to PPT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VDW to PPT in C#
    appDescription: Convert VDW to PPT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VDW to PPT in C# 
        description: Some description
        url: conversion/net/convert/vdw-to-ppt/#steps-to-convert-vdw-to-ppt-in-c
        steps:
        - name: Load source VDW file 
          text: Create an instance of Converter class and pass source VDW file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

VDW is the Visio Graphics Service file format that specifies the streams and storages required for rendering a Web drawing. A web drawing is a collection of drawing pages, shapes, fonts, images, data connections, and diagram update information that can be rendered as a vector or raster drawing. VDW files can be opened in Microsoft Visio as well but are primarily saved for use on the web.

## Steps to convert VDW to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDW file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDW file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDW file
using (var converter = new GroupDocs.Conversion.Converter("sample.vdw"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VDW to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**VDW to PPT converter**](https://products.groupdocs.app/conversion/vdw-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDW to PPT"](conversion/net/images/convert-to-ppt/convert-vdw-to-ppt.png)](https://products.groupdocs.app/conversion/vdw-to-ppt)