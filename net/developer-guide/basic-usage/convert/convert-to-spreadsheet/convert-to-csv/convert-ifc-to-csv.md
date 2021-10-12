---
id: convert-ifc-to-csv
url: conversion/net/convert-ifc-to-csv
title: Convert IFC to CSV
description: "IFC format represents Industry Foundation Classes (IFC) File Format with .ifc extension. Learn how to convert IFC to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IFC to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with IFC extension refer to  Industry Foundation Classes (IFC) file format that establishes international standards to import and export building objects and their properties. This file format provides interoperability between different software applications. Specifications for this file format are developed and maintained by buildingSMART International as its Data Standard.

## Steps to convert IFC to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IFC file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IFC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IFC file
using (var converter = new GroupDocs.Conversion.Converter("sample.ifc"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### IFC to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**IFC to CSV converter**](https://products.groupdocs.app/conversion/ifc-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IFC to CSV"](conversion/net/images/convert-to-csv/convert-ifc-to-csv.png)](https://products.groupdocs.app/conversion/ifc-to-csv)