---
id: svg-to-pptx
url: conversion/net/convert/svg-to-pptx
title: Convert SVG to PPTX
description: "SVG format represents Scalable Vector Graphics File with .svg extension. Learn how to convert SVG to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVG to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert SVG to PPTX in C#
    appDescription: Convert SVG to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert SVG to PPTX in C# 
        description: Quick guide about how to convert SVG to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/svg-to-pptx/#steps-to-convert-svg-to-pptx-in-c
        steps:
        - name: Load source SVG file 
          text: Create an instance of Converter class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

SVG files are Scalable Vector Graphics Files that use XML based text format for describing the appearance of image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text based description of such files make them independent of resolution. It is one of the mostly used format for building website and print graphics in order to achieve scalability.

## Steps to convert SVG to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVG file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVG file
using (var converter = new GroupDocs.Conversion.Converter("sample.svg"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVG to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**SVG to PPTX converter**](https://products.groupdocs.app/conversion/svg-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVG to PPTX"](conversion/net/images/convert-to-pptx/convert-svg-to-pptx.png)](https://products.groupdocs.app/conversion/svg-to-pptx)