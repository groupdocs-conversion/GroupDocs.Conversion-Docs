---
id: vtx-to-csv
url: conversion/net/convert/vtx-to-csv
title: Convert VTX to CSV
description: "VTX format represents Microsoft Visio Drawing Template with .vtx extension. Learn how to convert VTX to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VTX to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

## Steps to convert VTX to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VTX file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vtx"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VTX to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**VTX to CSV converter**](https://products.groupdocs.app/conversion/vtx-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VTX to CSV"](conversion/net/images/convert-to-csv/convert-vtx-to-csv.png)](https://products.groupdocs.app/conversion/vtx-to-csv)