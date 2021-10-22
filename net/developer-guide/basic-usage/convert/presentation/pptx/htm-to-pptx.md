---
id: htm-to-pptx
url: conversion/net/convert/htm-to-pptx
title: Convert HTM to PPTX
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert HTM to PPTX in C#
    appDescription: Convert HTM to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert HTM to PPTX in C# 
        description: Some description
        url: conversion/net/convert/htm-to-pptx/#steps-to-convert-htm-to-pptx-in-c
        steps:
        - name: Load source HTM file 
          text: Create an instance of Converter class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PPTX converter**](https://products.groupdocs.app/conversion/htm-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PPTX"](conversion/net/images/convert-to-pptx/convert-htm-to-pptx.png)](https://products.groupdocs.app/conversion/htm-to-pptx)