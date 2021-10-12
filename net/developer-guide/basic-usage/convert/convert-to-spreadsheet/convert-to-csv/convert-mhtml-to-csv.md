---
id: convert-mhtml-to-csv
url: conversion/net/convert-mhtml-to-csv
title: Convert MHTML to CSV
description: "MHTML format represents MIME Encapsulation of Aggregate HTML with .mhtml extension. Learn how to convert MHTML to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHTML to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

## Steps to convert MHTML to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHTML file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHTML file
using (var converter = new GroupDocs.Conversion.Converter("sample.mhtml"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHTML to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**MHTML to CSV converter**](https://products.groupdocs.app/conversion/mhtml-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHTML to CSV"](conversion/net/images/convert-to-csv/convert-mhtml-to-csv.png)](https://products.groupdocs.app/conversion/mhtml-to-csv)