---
id: convert-plt-to-xlsx
url: conversion/net/convert-plt-to-xlsx
title: Convert PLT to XLSX
description: "PLT format represents PLT (HPGL) with .plt extension. Learn how to convert PLT to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PLT to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An HPGL(Hewlett-Packard Graphics Language) file contains an instruction set for plotter control, developed by Hewlett-Packard. Hewlett-Packard plotters use this file to draw and print vector and raster content on the paper.

## Steps to convert PLT to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PLT file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.plt"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PLT to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**PLT to XLSX converter**](https://products.groupdocs.app/conversion/plt-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PLT to XLSX"](conversion/net/images/convert-to-xlsx/convert-plt-to-xlsx.png)](https://products.groupdocs.app/conversion/plt-to-xlsx)