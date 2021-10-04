---
id: convert-cf2-to-csv
url: conversion/net/convert-cf2-to-csv
title: Convert CF2 to CSV
description: "CF2 format represents Common File Format File with .cf2 extension. Learn how to convert CF2 to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CF2 to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .cf2 extension is a CAD file format that contains 3D package designs or other model data for die-cutting. Most of the CAD/CAM machines can process and cut these files. It was created by the National Space Science Data Center (NSSDC) to provide self-describing data storage and manipulation format that matches the structure of scientific data and applications such as statistical and numerical methods, visualization, and management. 

## Steps to convert CF2 to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CF2 file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CF2 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CF2 file
using (var converter = new GroupDocs.Conversion.Converter("sample.cf2"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CF2 to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**CF2 to CSV converter**](https://products.groupdocs.app/conversion/cf2-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CF2 to CSV"](conversion/net/images/convert-to-csv/convert-cf2-to-csv.png)](https://products.groupdocs.app/conversion/cf2-to-csv)