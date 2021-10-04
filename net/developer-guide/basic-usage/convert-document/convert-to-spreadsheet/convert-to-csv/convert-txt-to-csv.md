---
id: convert-txt-to-csv
url: conversion/net/convert-txt-to-csv
title: Convert TXT to CSV
description: "TXT format represents Plain Text File Format with .txt extension. Learn how to convert TXT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TXT to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

## Steps to convert TXT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TXT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TXT file
using (var converter = new GroupDocs.Conversion.Converter("sample.txt"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TXT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**TXT to CSV converter**](https://products.groupdocs.app/conversion/txt-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TXT to CSV"](conversion/net/images/convert-to-csv/convert-txt-to-csv.png)](https://products.groupdocs.app/conversion/txt-to-csv)