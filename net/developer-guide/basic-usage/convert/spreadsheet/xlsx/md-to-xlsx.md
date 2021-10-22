---
id: md-to-xlsx
url: conversion/net/convert/md-to-xlsx
title: Convert MD to XLSX
description: "MD format represents Markdown with .md extension. Learn how to convert MD to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MD to XLSX in C#
    appDescription: Convert MD to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MD to XLSX in C# 
        description: Some description
        url: conversion/net/convert/md-to-xlsx/#steps-to-convert-md-to-xlsx-in-c
        steps:
        - name: Load source MD file 
          text: Create an instance of Converter class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

## Steps to convert MD to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MD file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MD file
using (var converter = new GroupDocs.Conversion.Converter("sample.md"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MD to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**MD to XLSX converter**](https://products.groupdocs.app/conversion/md-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to XLSX"](conversion/net/images/convert-to-xlsx/convert-md-to-xlsx.png)](https://products.groupdocs.app/conversion/md-to-xlsx)