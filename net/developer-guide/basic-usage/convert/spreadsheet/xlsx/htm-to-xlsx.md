---
id: htm-to-xlsx
url: conversion/net/convert/htm-to-xlsx
title: Convert HTM to XLSX
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to XLSX converter**](https://products.groupdocs.app/conversion/htm-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to XLSX"](conversion/net/images/convert-to-xlsx/convert-htm-to-xlsx.png)](https://products.groupdocs.app/conversion/htm-to-xlsx)