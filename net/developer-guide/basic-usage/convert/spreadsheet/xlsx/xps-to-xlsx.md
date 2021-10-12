---
id: xps-to-xlsx
url: conversion/net/convert/xps-to-xlsx
title: Convert XPS to XLSX
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xps"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to XLSX converter**](https://products.groupdocs.app/conversion/xps-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to XLSX"](conversion/net/images/convert-to-xlsx/convert-xps-to-xlsx.png)](https://products.groupdocs.app/conversion/xps-to-xlsx)