---
id: rtf-to-csv
url: conversion/net/convert/rtf-to-csv
title: Convert RTF to CSV
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source RTF file
using (var converter = new GroupDocs.Conversion.Converter("sample.rtf"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to CSV converter**](https://products.groupdocs.app/conversion/rtf-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to CSV"](conversion/net/images/convert-to-csv/convert-rtf-to-csv.png)](https://products.groupdocs.app/conversion/rtf-to-csv)