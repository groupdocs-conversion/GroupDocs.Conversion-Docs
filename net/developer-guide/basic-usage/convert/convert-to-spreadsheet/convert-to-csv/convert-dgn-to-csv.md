---
id: convert-dgn-to-csv
url: conversion/net/convert-dgn-to-csv
title: Convert DGN to CSV
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (var converter = new GroupDocs.Conversion.Converter("sample.dgn"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DGN to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to CSV converter**](https://products.groupdocs.app/conversion/dgn-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to CSV"](conversion/net/images/convert-to-csv/convert-dgn-to-csv.png)](https://products.groupdocs.app/conversion/dgn-to-csv)