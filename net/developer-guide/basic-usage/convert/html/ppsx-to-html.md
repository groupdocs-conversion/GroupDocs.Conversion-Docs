---
id: ppsx-to-html
url: conversion/net/convert/ppsx-to-html
title: Convert PPSX to HTML
description: "PPSX format represents PowerPoint Open XML Slide Show with .ppsx extension. Learn how to convert PPSX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSX to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PPSX to HTML in C#
    appDescription: Convert PPSX to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PPSX to HTML in C# 
        description: Some description
        url: conversion/net/convert/ppsx-to-html/#steps-to-convert-ppsx-to-html-in-c
        steps:
        - name: Load source PPSX file 
          text: Create an instance of Converter class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of MarkupConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to HTML and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the MarkupConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

PPSX, Power Point Slide Show, file are created using Microsoft PowerPoint 2007 and above for Slide Show purpose. It is an update to the PPS file format that was supported by Microsoft PowerPoint 97-2003 versions. When a PPSX file is shared with another user and opened, it starts as PowerPoint show unlike PPTX file that opens in editable mode. The sequence of slide show is the same as in the original presentation. All the slides accompany the images, sounds and other embedded media accompany the presentation slides to the PPSX during the slideshow. 

## Steps to convert PPSX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPSX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppsx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPSX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSX to HTML converter**](https://products.groupdocs.app/conversion/ppsx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSX to HTML"](conversion/net/images/convert-to-html/convert-ppsx-to-html.png)](https://products.groupdocs.app/conversion/ppsx-to-html)