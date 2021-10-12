---
id: oxps-to-xlsx
url: conversion/net/convert/oxps-to-xlsx
title: Convert OXPS to XLSX
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

## Steps to convert OXPS to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OXPS file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OXPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OXPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.oxps"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OXPS to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to XLSX converter**](https://products.groupdocs.app/conversion/oxps-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to XLSX"](conversion/net/images/convert-to-xlsx/convert-oxps-to-xlsx.png)](https://products.groupdocs.app/conversion/oxps-to-xlsx)