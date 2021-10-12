---
id: log-to-xlsx
url: conversion/net/convert/log-to-xlsx
title: Convert LOG to XLSX
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to XLSX converter**](https://products.groupdocs.app/conversion/log-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to XLSX"](conversion/net/images/convert-to-xlsx/convert-log-to-xlsx.png)](https://products.groupdocs.app/conversion/log-to-xlsx)