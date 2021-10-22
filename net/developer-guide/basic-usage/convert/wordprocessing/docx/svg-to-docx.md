---
id: svg-to-docx
url: conversion/net/convert/svg-to-docx
title: Convert SVG to DOCX
description: "SVG format represents Scalable Vector Graphics File with .svg extension. Learn how to convert SVG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVG to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert SVG to DOCX in C#
    appDescription: Convert SVG to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert SVG to DOCX in C# 
        description: Some description
        url: conversion/net/convert/svg-to-docx/#steps-to-convert-svg-to-docx-in-c
        steps:
        - name: Load source SVG file 
          text: Create an instance of Converter class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

SVG files are Scalable Vector Graphics Files that use XML based text format for describing the appearance of image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text based description of such files make them independent of resolution. It is one of the mostly used format for building website and print graphics in order to achieve scalability.

## Steps to convert SVG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVG file
using (var converter = new GroupDocs.Conversion.Converter("sample.svg"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**SVG to DOCX converter**](https://products.groupdocs.app/conversion/svg-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVG to DOCX"](conversion/net/images/convert-to-docx/convert-svg-to-docx.png)](https://products.groupdocs.app/conversion/svg-to-docx)