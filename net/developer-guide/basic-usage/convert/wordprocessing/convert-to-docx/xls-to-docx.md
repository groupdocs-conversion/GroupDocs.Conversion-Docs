---
id: xls-to-docx
url: conversion/net/convert/xls-to-docx
title: Convert XLS to DOCX
description: "XLS format represents Microsoft Excel Binary File Format with .xls extension. Learn how to convert XLS to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLS to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

## Steps to convert XLS to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLS file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xls"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLS to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLS to DOCX converter**](https://products.groupdocs.app/conversion/xls-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLS to DOCX"](conversion/net/images/convert-to-docx/convert-xls-to-docx.png)](https://products.groupdocs.app/conversion/xls-to-docx)