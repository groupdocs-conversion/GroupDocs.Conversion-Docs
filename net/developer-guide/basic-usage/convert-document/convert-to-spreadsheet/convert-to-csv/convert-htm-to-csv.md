---
id: convert-htm-to-csv
url: conversion/net/convert-htm-to-csv
title: Convert HTM to CSV
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to CSV converter**](https://products.groupdocs.app/conversion/htm-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to CSV"](conversion/net/images/convert-to-csv/convert-htm-to-csv.png)](https://products.groupdocs.app/conversion/htm-to-csv)