---
id: convert-eml-to-csv
url: conversion/net/convert-eml-to-csv
title: Convert EML to CSV
description: "EML format represents E-Mail Message File with .eml extension. Learn how to convert EML to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EML to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EML file format represents email messages saved using Outlook and other relevant applications. Almost all emailing clients support this file format for its compliance with RFC-822 Internet Message Format Standard. Microsoft Outlook is default software for opening EML message types. EML files can be used for saving to disc as well as sending out to recipients using communication protocols.

## Steps to convert EML to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EML file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EML file
using (var converter = new GroupDocs.Conversion.Converter("sample.eml"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EML to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**EML to CSV converter**](https://products.groupdocs.app/conversion/eml-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EML to CSV"](conversion/net/images/convert-to-csv/convert-eml-to-csv.png)](https://products.groupdocs.app/conversion/eml-to-csv)