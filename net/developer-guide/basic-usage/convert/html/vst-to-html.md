---
id: vst-to-html
url: conversion/net/convert/vst-to-html
title: Convert VST to HTML
description: "VST format represents Visio Drawing Template with .vst extension. Learn how to convert VST to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VST to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VST to HTML in C#
    appDescription: Convert VST to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VST to HTML in C# 
        description: Some description
        url: conversion/net/convert/vst-to-html/#steps-to-convert-vst-to-html-in-c
        steps:
        - name: Load source VST file 
          text: Create an instance of Converter class and pass source VST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with VST extension are vector image files created with Microsoft Visio and act as templates for creating further files. These template files are in binary file format and contain the default layout and settings that are utilized for the creation of new Visio drawings. When a VST file is opened in Microsoft Visio, it contains the existing settings to continue working with the document. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VST to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VST file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VST file
using (var converter = new GroupDocs.Conversion.Converter("sample.vst"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VST to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**VST to HTML converter**](https://products.groupdocs.app/conversion/vst-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VST to HTML"](conversion/net/images/convert-to-html/convert-vst-to-html.png)](https://products.groupdocs.app/conversion/vst-to-html)