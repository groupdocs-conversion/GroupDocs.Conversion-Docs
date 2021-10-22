---
id: mpp-to-pptx
url: conversion/net/convert/mpp-to-pptx
title: Convert MPP to PPTX
description: "MPP format represents Microsoft Project File with .mpp extension. Learn how to convert MPP to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPP to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MPP to PPTX in C#
    appDescription: Convert MPP to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MPP to PPTX in C# 
        description: Some description
        url: conversion/net/convert/mpp-to-pptx/#steps-to-convert-mpp-to-pptx-in-c
        steps:
        - name: Load source MPP file 
          text: Create an instance of Converter class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A file with MPP extension is Microsoft Project data file that stores information related to project management in an integrated manner. It is proprietary file format developed by Microsoft as file format for Microsoft Project (MSP) which is a project management application software. Besides MPP, MSP supports other file formats as well like project XML schema. Several APIs and applications provide the facility to convert MPP file format to others.

## Steps to convert MPP to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPP file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPP file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpp"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPP to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**MPP to PPTX converter**](https://products.groupdocs.app/conversion/mpp-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPP to PPTX"](conversion/net/images/convert-to-pptx/convert-mpp-to-pptx.png)](https://products.groupdocs.app/conversion/mpp-to-pptx)