---
id: jpc-to-pptx
url: conversion/net/convert/jpc-to-pptx
title: Convert JPC to PPTX
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JPC to PPTX in C#
    appDescription: Convert JPC to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JPC to PPTX in C# 
        description: Quick guide about how to convert JPC to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/jpc-to-pptx/#steps-to-convert-jpc-to-pptx-in-c
        steps:
        - name: Load source JPC file 
          text: Create an instance of Converter class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to PPTX converter**](https://products.groupdocs.app/conversion/jpc-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to PPTX"](conversion/net/images/convert-to-pptx/convert-jpc-to-pptx.png)](https://products.groupdocs.app/conversion/jpc-to-pptx)