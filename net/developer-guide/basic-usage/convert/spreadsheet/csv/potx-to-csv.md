---
id: potx-to-csv
url: conversion/net/convert/potx-to-csv
title: Convert POTX to CSV
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to CSV in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert POTX to CSV in C#
    appDescription: Convert POTX to CSV natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert POTX to CSV in C# 
        description: Some description
        url: conversion/net/convert/potx-to-csv/#steps-to-convert-potx-to-csv-in-c
        steps:
        - name: Load source POTX file 
          text: Create an instance of Converter class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

## Steps to convert POTX to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTX file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.potx"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTX to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to CSV converter**](https://products.groupdocs.app/conversion/potx-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to CSV"](conversion/net/images/convert-to-csv/convert-potx-to-csv.png)](https://products.groupdocs.app/conversion/potx-to-csv)