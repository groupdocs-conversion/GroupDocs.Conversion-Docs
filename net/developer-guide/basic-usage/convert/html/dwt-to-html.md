---
id: dwt-to-html
url: conversion/net/convert/dwt-to-html
title: Convert DWT to HTML
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWT to HTML in C#
    appDescription: Convert DWT to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWT to HTML in C# 
        description: Quick guide about how to convert DWT to HTML in C# with high performance and accuracy.
        url: conversion/net/convert/dwt-to-html/#steps-to-convert-dwt-to-html-in-c
        steps:
        - name: Load source DWT file 
          text: Create an instance of Converter class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwt"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to HTML converter**](https://products.groupdocs.app/conversion/dwt-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to HTML"](conversion/net/images/convert-to-html/convert-dwt-to-html.png)](https://products.groupdocs.app/conversion/dwt-to-html)