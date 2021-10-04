---
id: convert-mht-to-csv
url: conversion/net/convert-mht-to-csv
title: Convert MHT to CSV
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mht"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to CSV converter**](https://products.groupdocs.app/conversion/mht-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to CSV"](conversion/net/images/convert-to-csv/convert-mht-to-csv.png)](https://products.groupdocs.app/conversion/mht-to-csv)