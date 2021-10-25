---
id: dwfx-to-xlsx
url: conversion/net/convert/dwfx-to-xlsx
title: Convert DWFX to XLSX
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWFX to XLSX in C#
    appDescription: Convert DWFX to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWFX to XLSX in C# 
        description: Quick guide about how to convert DWFX to XLSX in C# with high performance and accuracy.
        url: conversion/net/convert/dwfx-to-xlsx/#steps-to-convert-dwfx-to-xlsx-in-c
        steps:
        - name: Load source DWFX file 
          text: Create an instance of Converter class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwfx"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWFX to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to XLSX converter**](https://products.groupdocs.app/conversion/dwfx-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to XLSX"](conversion/net/images/convert-to-xlsx/convert-dwfx-to-xlsx.png)](https://products.groupdocs.app/conversion/dwfx-to-xlsx)