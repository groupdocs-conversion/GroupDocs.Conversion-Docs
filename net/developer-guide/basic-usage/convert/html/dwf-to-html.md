---
id: dwf-to-html
url: conversion/net/convert/dwf-to-html
title: Convert DWF to HTML
description: "DWF format represents Design Web Format with .dwf extension. Learn how to convert DWF to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWF to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWF to HTML in C#
    appDescription: Convert DWF to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWF to HTML in C# 
        description: Some description
        url: conversion/net/convert/dwf-to-html/#steps-to-convert-dwf-to-html-in-c
        steps:
        - name: Load source DWF file 
          text: Create an instance of Converter class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing, or printing design files. It contains graphics and text as part of design data and reduces the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn't require the recipient to know about the usage of CAD software that created the original drawing.

## Steps to convert DWF to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWF file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwf"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWF to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**DWF to HTML converter**](https://products.groupdocs.app/conversion/dwf-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWF to HTML"](conversion/net/images/convert-to-html/convert-dwf-to-html.png)](https://products.groupdocs.app/conversion/dwf-to-html)