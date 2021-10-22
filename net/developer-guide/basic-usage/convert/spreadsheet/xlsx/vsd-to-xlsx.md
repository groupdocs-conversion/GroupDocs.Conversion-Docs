---
id: vsd-to-xlsx
url: conversion/net/convert/vsd-to-xlsx
title: Convert VSD to XLSX
description: "VSD format represents Visio Drawing File Format with .vsd extension. Learn how to convert VSD to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSD to XLSX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSD to XLSX in C#
    appDescription: Convert VSD to XLSX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSD to XLSX in C# 
        description: Some description
        url: conversion/net/convert/vsd-to-xlsx/#steps-to-convert-vsd-to-xlsx-in-c
        steps:
        - name: Load source VSD file 
          text: Create an instance of Converter class and pass source VSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

VSD files are drawings created with Microsoft Visio application to represent variety of graphical objects and the interconnection between these. Such drawings can contain visual objects such as visual objects, flow charts, UML diagram, information flow, organizational charts, software diagrams, network layout, database models, objects mapping and other similar information. Microsoft Visio offers the capability to convert Visio files to a number of different file formats including PNG, BMP, PDF and others.

## Steps to convert VSD to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSD file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSD file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsd"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSD to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSD to XLSX converter**](https://products.groupdocs.app/conversion/vsd-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSD to XLSX"](conversion/net/images/convert-to-xlsx/convert-vsd-to-xlsx.png)](https://products.groupdocs.app/conversion/vsd-to-xlsx)