---
id: jpm-to-xlsx
url: conversion/net/convert/jpm-to-xlsx
title: Convert JPM to XLSX
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to XLSX converter**](https://products.groupdocs.app/conversion/jpm-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to XLSX"](conversion/net/images/convert-to-xlsx/convert-jpm-to-xlsx.png)](https://products.groupdocs.app/conversion/jpm-to-xlsx)