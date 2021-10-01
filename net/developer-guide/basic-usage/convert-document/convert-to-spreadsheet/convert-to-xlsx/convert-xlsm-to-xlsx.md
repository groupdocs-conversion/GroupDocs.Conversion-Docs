---
id: convert-xlsm-to-xlsx
url: conversion/net/convert-xlsm-to-xlsx
title: Convert XLSM to XLSX
description: "XLSM format represents Microsoft Excel Macro-Enabled Spreadsheet with .xlsm extension. Learn how to convert XLSM to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSM to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLSM extension is a type of Spreasheet files that support Macros. From application point of view, a Macro is set of instructions that are used for automating processes. A macro is used to record the steps that are performed repeatedly and facilitates performing the actions by running the macro again. Macros are programmed with Microsoft's Visual Basic for Applications (VBA) from within the Excel Workbook using the Visual Basic Editor and can be run/debug directly from there.

## Steps to convert XLSM to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSM file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsm"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSM to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSM to XLSX converter**](https://products.groupdocs.app/conversion/xlsm-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSM to XLSX"](conversion/net/images/convert-to-xlsx/convert-xlsm-to-xlsx.png)](https://products.groupdocs.app/conversion/xlsm-to-xlsx)