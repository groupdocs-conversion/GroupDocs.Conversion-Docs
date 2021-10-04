---
id: convert-fodp-to-csv
url: conversion/net/convert-fodp-to-csv
title: Convert FODP to CSV
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to CSV converter**](https://products.groupdocs.app/conversion/fodp-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to CSV"](conversion/net/images/convert-to-csv/convert-fodp-to-csv.png)](https://products.groupdocs.app/conversion/fodp-to-csv)