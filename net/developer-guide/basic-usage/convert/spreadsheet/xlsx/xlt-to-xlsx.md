---
id: xlt-to-xlsx
url: conversion/net/convert/xlt-to-xlsx
title: Convert XLT to XLSX
description: "XLT format represents Microsoft Excel Template with .xlt extension. Learn how to convert XLT to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLT to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

## Steps to convert XLT to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLT file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlt"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLT to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLT to XLSX converter**](https://products.groupdocs.app/conversion/xlt-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLT to XLSX"](conversion/net/images/convert-to-xlsx/convert-xlt-to-xlsx.png)](https://products.groupdocs.app/conversion/xlt-to-xlsx)