---
id: one-to-pptx
url: conversion/net/convert/one-to-pptx
title: Convert ONE to PPTX
description: "ONE format represents Microsoft OneNote File Format with .one extension. Learn how to convert ONE to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ONE to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ONE to PPTX in C#
    appDescription: Convert ONE to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ONE to PPTX in C# 
        description: Quick guide about how to convert ONE to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/one-to-pptx/#steps-to-convert-one-to-pptx-in-c
        steps:
        - name: Load source ONE file 
          text: Create an instance of Converter class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draftpad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips.

## Steps to convert ONE to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ONE file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ONE file
using (var converter = new GroupDocs.Conversion.Converter("sample.one"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ONE to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**ONE to PPTX converter**](https://products.groupdocs.app/conversion/one-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ONE to PPTX"](conversion/net/images/convert-to-pptx/convert-one-to-pptx.png)](https://products.groupdocs.app/conversion/one-to-pptx)