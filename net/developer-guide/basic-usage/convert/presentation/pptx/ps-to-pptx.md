---
id: ps-to-pptx
url: conversion/net/convert/ps-to-pptx
title: Convert PS to PPTX
description: "PS format represents PostScript (PS) with .ps extension. Learn how to convert PS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PS to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PS to PPTX in C#
    appDescription: Convert PS to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PS to PPTX in C# 
        description: Some description
        url: conversion/net/convert/ps-to-pptx/#steps-to-convert-ps-to-pptx-in-c
        steps:
        - name: Load source PS file 
          text: Create an instance of Converter class and pass source PS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straightforward interpretation.

## Steps to convert PS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ps"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**PS to PPTX converter**](https://products.groupdocs.app/conversion/ps-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PS to PPTX"](conversion/net/images/convert-to-pptx/convert-ps-to-pptx.png)](https://products.groupdocs.app/conversion/ps-to-pptx)