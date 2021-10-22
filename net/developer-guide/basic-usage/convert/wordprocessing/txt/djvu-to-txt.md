---
id: djvu-to-txt
url: conversion/net/convert/djvu-to-txt
title: Convert DJVU to TXT
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DJVU to TXT in C#
    appDescription: Convert DJVU to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DJVU to TXT in C# 
        description: Some description
        url: conversion/net/convert/djvu-to-txt/#steps-to-convert-djvu-to-txt-in-c
        steps:
        - name: Load source DJVU file 
          text: Create an instance of Converter class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TXT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to TXT converter**](https://products.groupdocs.app/conversion/djvu-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to TXT"](conversion/net/images/convert-to-txt/convert-djvu-to-txt.png)](https://products.groupdocs.app/conversion/djvu-to-txt)