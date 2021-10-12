---
id: epub-to-csv
url: conversion/net/convert/epub-to-csv
title: Convert EPUB to CSV
description: "EPUB format represents Digital E-Book File Format with .epub extension. Learn how to convert EPUB to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPUB to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

## Steps to convert EPUB to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPUB file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPUB file
using (var converter = new GroupDocs.Conversion.Converter("sample.epub"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPUB to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**EPUB to CSV converter**](https://products.groupdocs.app/conversion/epub-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPUB to CSV"](conversion/net/images/convert-to-csv/convert-epub-to-csv.png)](https://products.groupdocs.app/conversion/epub-to-csv)