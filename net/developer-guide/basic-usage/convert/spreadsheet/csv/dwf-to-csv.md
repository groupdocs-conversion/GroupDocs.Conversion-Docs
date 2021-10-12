---
id: dwf-to-csv
url: conversion/net/convert/dwf-to-csv
title: Convert DWF to CSV
description: "DWF format represents Design Web Format with .dwf extension. Learn how to convert DWF to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWF to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing, or printing design files. It contains graphics and text as part of design data and reduces the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn't require the recipient to know about the usage of CAD software that created the original drawing.

## Steps to convert DWF to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWF file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwf"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWF to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**DWF to CSV converter**](https://products.groupdocs.app/conversion/dwf-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWF to CSV"](conversion/net/images/convert-to-csv/convert-dwf-to-csv.png)](https://products.groupdocs.app/conversion/dwf-to-csv)