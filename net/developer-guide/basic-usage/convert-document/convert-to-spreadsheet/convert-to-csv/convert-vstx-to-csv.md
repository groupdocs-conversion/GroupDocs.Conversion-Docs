---
id: convert-vstx-to-csv
url: conversion/net/convert-vstx-to-csv
title: Convert VSTX to CSV
description: "VSTX format represents Microsoft Visio File Format with .vstx extension. Learn how to convert VSTX to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTX to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSTX extensions are drawing template files created with Microsoft Visio 2013 and above. These VSTX files provide a starting point for creating Visio drawings, saved as VSDX files, with default layout and settings. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VSTX to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSTX file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vstx"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSTX to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTX to CSV converter**](https://products.groupdocs.app/conversion/vstx-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTX to CSV"](conversion/net/images/convert-to-csv/convert-vstx-to-csv.png)](https://products.groupdocs.app/conversion/vstx-to-csv)