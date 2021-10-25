---
id: xlt-to-csv
url: conversion/net/convert/xlt-to-csv
title: Convert XLT to CSV
description: "XLT format represents Microsoft Excel Template with .xlt extension. Learn how to convert XLT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLT to CSV in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert XLT to CSV in C#
    appDescription: Convert XLT to CSV natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert XLT to CSV in C# 
        description: Quick guide about how to convert XLT to CSV in C# with high performance and accuracy.
        url: conversion/net/convert/xlt-to-csv/#steps-to-convert-xlt-to-csv-in-c
        steps:
        - name: Load source XLT file 
          text: Create an instance of Converter class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to CSV and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the SpreadsheetConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

## Steps to convert XLT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlt"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**XLT to CSV converter**](https://products.groupdocs.app/conversion/xlt-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLT to CSV"](conversion/net/images/convert-to-csv/convert-xlt-to-csv.png)](https://products.groupdocs.app/conversion/xlt-to-csv)