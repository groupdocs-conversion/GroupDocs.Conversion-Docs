---
id: psd-to-pptx
url: conversion/net/convert/psd-to-pptx
title: Convert PSD to PPTX
description: "PSD format represents Adobe Photoshop Document with .psd extension. Learn how to convert PSD to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PSD to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PSD to PPTX in C#
    appDescription: Convert PSD to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PSD to PPTX in C# 
        description: Quick guide about how to convert PSD to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/psd-to-pptx/#steps-to-convert-psd-to-pptx-in-c
        steps:
        - name: Load source PSD file 
          text: Create an instance of Converter class and pass source PSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

PSD, Photoshop Document, represents Adobe Photoshop's native file format used for graphics designing and development. PSD files may include image layers, adjustment layers, layer masks, annotations, file information, keywords, and other Photoshop-specific elements. Photoshop files have default extension as PSD and have a maximum height and width of 30,000 pixels, and a length limit of two gigabytes.

## Steps to convert PSD to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PSD file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PSD file
using (var converter = new GroupDocs.Conversion.Converter("sample.psd"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PSD to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**PSD to PPTX converter**](https://products.groupdocs.app/conversion/psd-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PSD to PPTX"](conversion/net/images/convert-to-pptx/convert-psd-to-pptx.png)](https://products.groupdocs.app/conversion/psd-to-pptx)