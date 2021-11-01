---
id: tif-to-pptx
url: conversion/net/convert/tif-to-pptx
title: Convert TIF to PPTX
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TIF to PPTX in C#
    appDescription: Convert TIF to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TIF to PPTX in C# 
        description: Quick guide about how to convert TIF to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/tif-to-pptx/#steps-to-convert-tif-to-pptx-in-c
        steps:
        - name: Load source TIF file 
          text: Create an instance of Converter class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tif"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to PPTX converter**](https://products.groupdocs.app/conversion/tif-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to PPTX"](conversion/net/images/convert-to-pptx/convert-tif-to-pptx.png)](https://products.groupdocs.app/conversion/tif-to-pptx)