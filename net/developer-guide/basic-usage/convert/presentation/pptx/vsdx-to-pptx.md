---
id: vsdx-to-pptx
url: conversion/net/convert/vsdx-to-pptx
title: Convert VSDX to PPTX
description: "VSDX format represents Microsoft Visio File Format with .vsdx extension. Learn how to convert VSDX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDX to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSDX to PPTX in C#
    appDescription: Convert VSDX to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSDX to PPTX in C# 
        description: Some description
        url: conversion/net/convert/vsdx-to-pptx/#steps-to-convert-vsdx-to-pptx-in-c
        steps:
        - name: Load source VSDX file 
          text: Create an instance of Converter class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

## Steps to convert VSDX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsdx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to PPTX converter**](https://products.groupdocs.app/conversion/vsdx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to PPTX"](conversion/net/images/convert-to-pptx/convert-vsdx-to-pptx.png)](https://products.groupdocs.app/conversion/vsdx-to-pptx)