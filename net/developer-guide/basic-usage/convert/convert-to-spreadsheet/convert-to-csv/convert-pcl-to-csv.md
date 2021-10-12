---
id: convert-pcl-to-csv
url: conversion/net/convert-pcl-to-csv
title: Convert PCL to CSV
description: "PCL format represents Printer Command Language Document with .pcl extension. Learn how to convert PCL to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PCL to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PCL stands for Printer Command Language which is a Page Description Language introduced by Hewlett Packard (HP). HP created PCL to provide an efficient way of controlling printer features across many different printing devices. The format was originally developed for HP’s dot-matrix and Inkjet printers but has been part of various thermal, matrix, and page printers with the passage of time. The format underwent several different revisions, resulting in different versions where each version was enhanced to meet the demands of time with respect to the printer control features

## Steps to convert PCL to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PCL file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PCL file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PCL file
using (var converter = new GroupDocs.Conversion.Converter("sample.pcl"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PCL to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**PCL to CSV converter**](https://products.groupdocs.app/conversion/pcl-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PCL to CSV"](conversion/net/images/convert-to-csv/convert-pcl-to-csv.png)](https://products.groupdocs.app/conversion/pcl-to-csv)