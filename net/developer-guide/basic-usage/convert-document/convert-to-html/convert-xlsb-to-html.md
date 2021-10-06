---
id: convert-xlsb-to-html
url: conversion/net/convert-xlsb-to-html
title: Convert XLSB to HTML
description: "XLSB format represents Microsoft Excel Binary Spreadsheet File with .xlsb extension. Learn how to convert XLSB to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSB to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSB file format specifies the Excel Binary File Format, which is a collection of records and structures that specify Excel workbook content. The content can include unstructured or semi-structured tables of numbers, text, or both numbers and text, formulas, external data connections, charts and images. Unlike XLSX (which is based on Open XML file format), the XLSB represents binary Excel workbook file.

## Steps to convert XLSB to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSB file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSB file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsb"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSB to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSB to HTML converter**](https://products.groupdocs.app/conversion/xlsb-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSB to HTML"](conversion/net/images/convert-to-html/convert-xlsb-to-html.png)](https://products.groupdocs.app/conversion/xlsb-to-html)