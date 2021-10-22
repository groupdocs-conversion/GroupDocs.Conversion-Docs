---
id: djvu-to-xlsx
url: conversion/net/convert/djvu-to-xlsx
title: Convert DJVU to XLSX
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DJVU to XLSX in C#
    appDescription: Convert DJVU to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DJVU to XLSX in C# 
        description: Some description
        url: conversion/net/convert/djvu-to-xlsx/#steps-to-convert-djvu-to-xlsx-in-c
        steps:
        - name: Load source DJVU file 
          text: Create an instance of Converter class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to XLSX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the SpreadsheetConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to XLSX converter**](https://products.groupdocs.app/conversion/djvu-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to XLSX"](conversion/net/images/convert-to-xlsx/convert-djvu-to-xlsx.png)](https://products.groupdocs.app/conversion/djvu-to-xlsx)