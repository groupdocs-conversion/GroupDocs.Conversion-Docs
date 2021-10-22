---
id: one-to-xlsx
url: conversion/net/convert/one-to-xlsx
title: Convert ONE to XLSX
description: "ONE format represents Microsoft OneNote File Format with .one extension. Learn how to convert ONE to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ONE to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ONE to XLSX in C#
    appDescription: Convert ONE to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ONE to XLSX in C# 
        description: Some description
        url: conversion/net/convert/one-to-xlsx/#steps-to-convert-one-to-xlsx-in-c
        steps:
        - name: Load source ONE file 
          text: Create an instance of Converter class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draftpad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips.

## Steps to convert ONE to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ONE file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ONE file
using (var converter = new GroupDocs.Conversion.Converter("sample.one"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ONE to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**ONE to XLSX converter**](https://products.groupdocs.app/conversion/one-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ONE to XLSX"](conversion/net/images/convert-to-xlsx/convert-one-to-xlsx.png)](https://products.groupdocs.app/conversion/one-to-xlsx)