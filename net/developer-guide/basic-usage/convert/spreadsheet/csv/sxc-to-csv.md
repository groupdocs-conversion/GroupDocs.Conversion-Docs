---
id: sxc-to-csv
url: conversion/net/convert/sxc-to-csv
title: Convert SXC to CSV
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to CSV converter**](https://products.groupdocs.app/conversion/sxc-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to CSV"](conversion/net/images/convert-to-csv/convert-sxc-to-csv.png)](https://products.groupdocs.app/conversion/sxc-to-csv)