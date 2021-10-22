---
id: j2c-to-xls
url: conversion/net/convert/j2c-to-xls
title: Convert J2C to XLS
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to XLS in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert J2C to XLS in C#
    appDescription: Convert J2C to XLS natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert J2C to XLS in C# 
        description: Some description
        url: conversion/net/convert/j2c-to-xls/#steps-to-convert-j2c-to-xls-in-c
        steps:
        - name: Load source J2C file 
          text: Create an instance of Converter class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to XLS and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the SpreadsheetConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2c"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2C to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to XLS converter**](https://products.groupdocs.app/conversion/j2c-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to XLS"](conversion/net/images/convert-to-xls/convert-j2c-to-xls.png)](https://products.groupdocs.app/conversion/j2c-to-xls)