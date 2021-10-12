---
id: xlsx-to-html
url: conversion/net/convert/xlsx-to-html
title: Convert XLSX to HTML
description: "XLSX format represents Microsoft Excel Open XML Spreadsheet with .xlsx extension. Learn how to convert XLSX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSX to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

## Steps to convert XLSX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSX to HTML converter**](https://products.groupdocs.app/conversion/xlsx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSX to HTML"](conversion/net/images/convert-to-html/convert-xlsx-to-html.png)](https://products.groupdocs.app/conversion/xlsx-to-html)