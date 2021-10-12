---
id: xlsb-to-xlsx
url: conversion/net/convert/xlsb-to-xlsx
title: Convert XLSB to XLSX
description: "XLSB format represents Microsoft Excel Binary Spreadsheet File with .xlsb extension. Learn how to convert XLSB to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSB to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSB file format specifies the Excel Binary File Format, which is a collection of records and structures that specify Excel workbook content. The content can include unstructured or semi-structured tables of numbers, text, or both numbers and text, formulas, external data connections, charts and images. Unlike XLSX (which is based on Open XML file format), the XLSB represents binary Excel workbook file.

## Steps to convert XLSB to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSB file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSB file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsb"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSB to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSB to XLSX converter**](https://products.groupdocs.app/conversion/xlsb-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSB to XLSX"](conversion/net/images/convert-to-xlsx/convert-xlsb-to-xlsx.png)](https://products.groupdocs.app/conversion/xlsb-to-xlsx)