---
id: convert-vdx-to-csv
url: conversion/net/convert-vdx-to-csv
title: Convert VDX to CSV
description: "VDX format represents Microsoft Visio XML Drawing File Format with .vdx extension. Learn how to convert VDX to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDX to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Any drawing or chart created in Microsoft Visio, but saved in XML format has a VDX extension. A Visio drawing XML file is created in Visio software, which is developed by Microsoft. Microsoft Visio has the capability to generate visual documents that can be used in presentations and documents. The Visio drawing XML file contains the visual objects and metadata details of the visual elements.

## Steps to convert VDX to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDX file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vdx"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VDX to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**VDX to CSV converter**](https://products.groupdocs.app/conversion/vdx-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDX to CSV"](conversion/net/images/convert-to-csv/convert-vdx-to-csv.png)](https://products.groupdocs.app/conversion/vdx-to-csv)