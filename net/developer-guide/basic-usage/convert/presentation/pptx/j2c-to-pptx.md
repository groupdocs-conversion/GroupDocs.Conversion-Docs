---
id: j2c-to-pptx
url: conversion/net/convert/j2c-to-pptx
title: Convert J2C to PPTX
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert J2C to PPTX in C#
    appDescription: Convert J2C to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert J2C to PPTX in C# 
        description: Some description
        url: conversion/net/convert/j2c-to-pptx/#steps-to-convert-j2c-to-pptx-in-c
        steps:
        - name: Load source J2C file 
          text: Create an instance of Converter class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2c"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2C to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to PPTX converter**](https://products.groupdocs.app/conversion/j2c-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to PPTX"](conversion/net/images/convert-to-pptx/convert-j2c-to-pptx.png)](https://products.groupdocs.app/conversion/j2c-to-pptx)