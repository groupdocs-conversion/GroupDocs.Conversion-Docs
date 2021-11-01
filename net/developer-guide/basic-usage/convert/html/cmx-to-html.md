---
id: cmx-to-html
url: conversion/net/convert/cmx-to-html
title: Convert CMX to HTML
description: "CMX format represents Corel Metafile Exchange Image File with .cmx extension. Learn how to convert CMX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CMX to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CMX to HTML in C#
    appDescription: Convert CMX to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CMX to HTML in C# 
        description: Quick guide about how to convert CMX to HTML in C# with high performance and accuracy.
        url: conversion/net/convert/cmx-to-html/#steps-to-convert-cmx-to-html-in-c
        steps:
        - name: Load source CMX file 
          text: Create an instance of Converter class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with CMX extension are Corel Exchange image file format (also known as Corel Metafile Exchange) that is used as presentation by CorelSuite applications. It contains image data as vector graphics as well as metadata that describes the image. CMX files can be opened by CorelDraw, Corel Presentations, Paint Shop Pro and some versions of Adobe Illustrator. CMX files can be converted to other formats such as JPG and EPS.

## Steps to convert CMX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CMX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CMX file
using (var converter = new GroupDocs.Conversion.Converter("sample.cmx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CMX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**CMX to HTML converter**](https://products.groupdocs.app/conversion/cmx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CMX to HTML"](conversion/net/images/convert-to-html/convert-cmx-to-html.png)](https://products.groupdocs.app/conversion/cmx-to-html)