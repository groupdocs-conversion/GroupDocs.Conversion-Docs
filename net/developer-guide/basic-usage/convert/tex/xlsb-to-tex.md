---
id: xlsb-to-tex
url: conversion/net/convert/xlsb-to-tex
title: Convert XLSB to TEX
description: "XLSB format represents Microsoft Excel Binary Spreadsheet File with .xlsb extension. Learn how to convert XLSB to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSB to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert XLSB to TEX in C#
    appDescription: Convert XLSB to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert XLSB to TEX in C# 
        description: Some description
        url: conversion/net/convert/xlsb-to-tex/#steps-to-convert-xlsb-to-tex-in-c
        steps:
        - name: Load source XLSB file 
          text: Create an instance of Converter class and pass source XLSB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TEX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

XLSB file format specifies the Excel Binary File Format, which is a collection of records and structures that specify Excel workbook content. The content can include unstructured or semi-structured tables of numbers, text, or both numbers and text, formulas, external data connections, charts and images. Unlike XLSX (which is based on Open XML file format), the XLSB represents binary Excel workbook file.

## Steps to convert XLSB to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSB file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSB file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsb"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSB to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSB to TEX converter**](https://products.groupdocs.app/conversion/xlsb-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSB to TEX"](conversion/net/images/convert-to-tex/convert-xlsb-to-tex.png)](https://products.groupdocs.app/conversion/xlsb-to-tex)