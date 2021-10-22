---
id: odp-to-txt
url: conversion/net/convert/odp-to-txt
title: Convert ODP to TXT
description: "ODP format represents OpenDocument Presentation File Format with .odp extension. Learn how to convert ODP to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODP to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ODP to TXT in C#
    appDescription: Convert ODP to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ODP to TXT in C# 
        description: Some description
        url: conversion/net/convert/odp-to-txt/#steps-to-convert-odp-to-txt-in-c
        steps:
        - name: Load source ODP file 
          text: Create an instance of Converter class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

## Steps to convert ODP to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODP file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.odp"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODP to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**ODP to TXT converter**](https://products.groupdocs.app/conversion/odp-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODP to TXT"](conversion/net/images/convert-to-txt/convert-odp-to-txt.png)](https://products.groupdocs.app/conversion/odp-to-txt)