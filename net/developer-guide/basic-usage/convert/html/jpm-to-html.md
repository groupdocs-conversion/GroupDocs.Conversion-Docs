---
id: jpm-to-html
url: conversion/net/convert/jpm-to-html
title: Convert JPM to HTML
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JPM to HTML in C#
    appDescription: Convert JPM to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JPM to HTML in C# 
        description: Some description
        url: conversion/net/convert/jpm-to-html/#steps-to-convert-jpm-to-html-in-c
        steps:
        - name: Load source JPM file 
          text: Create an instance of Converter class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to HTML converter**](https://products.groupdocs.app/conversion/jpm-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to HTML"](conversion/net/images/convert-to-html/convert-jpm-to-html.png)](https://products.groupdocs.app/conversion/jpm-to-html)