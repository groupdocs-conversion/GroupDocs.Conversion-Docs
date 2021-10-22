---
id: log-to-html
url: conversion/net/convert/log-to-html
title: Convert LOG to HTML
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert LOG to HTML in C#
    appDescription: Convert LOG to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert LOG to HTML in C# 
        description: Some description
        url: conversion/net/convert/log-to-html/#steps-to-convert-log-to-html-in-c
        steps:
        - name: Load source LOG file 
          text: Create an instance of Converter class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to HTML converter**](https://products.groupdocs.app/conversion/log-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to HTML"](conversion/net/images/convert-to-html/convert-log-to-html.png)](https://products.groupdocs.app/conversion/log-to-html)