---
id: convert-xps-to-csv
url: conversion/net/convert-xps-to-csv
title: Convert XPS to CSV
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xps"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to CSV converter**](https://products.groupdocs.app/conversion/xps-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to CSV"](conversion/net/images/convert-to-csv/convert-xps-to-csv.png)](https://products.groupdocs.app/conversion/xps-to-csv)