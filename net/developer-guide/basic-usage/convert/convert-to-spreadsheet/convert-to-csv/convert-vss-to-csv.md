---
id: convert-vss-to-csv
url: conversion/net/convert-vss-to-csv
title: Convert VSS to CSV
description: "VSS format represents Visio Stencil File with .vss extension. Learn how to convert VSS to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSS to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSS is stencil files created with Microsoft Visio 2007 and earlier. A relatively new file format is VSSX that was introduced with Microsoft Visio 2013. Stencil files provide drawing objects that can be included in a VSD Visio drawing. Microsoft Visio is used for creating drawing elements such as a collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping, and other similar information.

## Steps to convert VSS to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSS file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSS file
using (var converter = new GroupDocs.Conversion.Converter("sample.vss"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSS to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**VSS to CSV converter**](https://products.groupdocs.app/conversion/vss-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSS to CSV"](conversion/net/images/convert-to-csv/convert-vss-to-csv.png)](https://products.groupdocs.app/conversion/vss-to-csv)