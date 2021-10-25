---
id: txt-to-xlsx
url: conversion/net/convert/txt-to-xlsx
title: Convert TXT to XLSX
description: "TXT format represents Plain Text File Format with .txt extension. Learn how to convert TXT to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TXT to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TXT to XLSX in C#
    appDescription: Convert TXT to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TXT to XLSX in C# 
        description: Quick guide about how to convert TXT to XLSX in C# with high performance and accuracy.
        url: conversion/net/convert/txt-to-xlsx/#steps-to-convert-txt-to-xlsx-in-c
        steps:
        - name: Load source TXT file 
          text: Create an instance of Converter class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

## Steps to convert TXT to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TXT file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TXT file
using (var converter = new GroupDocs.Conversion.Converter("sample.txt"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TXT to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**TXT to XLSX converter**](https://products.groupdocs.app/conversion/txt-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TXT to XLSX"](conversion/net/images/convert-to-xlsx/convert-txt-to-xlsx.png)](https://products.groupdocs.app/conversion/txt-to-xlsx)