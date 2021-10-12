---
id: convert-djvu-to-xlsx
url: conversion/net/convert-djvu-to-xlsx
title: Convert DJVU to XLSX
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to XLSX converter**](https://products.groupdocs.app/conversion/djvu-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to XLSX"](conversion/net/images/convert-to-xlsx/convert-djvu-to-xlsx.png)](https://products.groupdocs.app/conversion/djvu-to-xlsx)