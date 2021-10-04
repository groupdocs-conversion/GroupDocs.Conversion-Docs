---
id: convert-stl-to-csv
url: conversion/net/convert-stl-to-csv
title: Convert STL to CSV
description: "STL format represents Stereolithography with .stl extension. Learn how to convert STL to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert STL to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

STL, an abbreviation for stereolithography, is an interchangeable file format that represents 3-dimensional surface geometry. The file format finds its usage in several fields such as rapid prototyping, 3D printing, and computer-aided manufacturing. It represents a surface as a series of small triangles, known as facets, where each facet is described by a perpendicular direction and three points representing the vertices of the triangle.

## Steps to convert STL to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the STL file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source STL file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source STL file
using (var converter = new GroupDocs.Conversion.Converter("sample.stl"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### STL to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**STL to CSV converter**](https://products.groupdocs.app/conversion/stl-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert STL to CSV"](conversion/net/images/convert-to-csv/convert-stl-to-csv.png)](https://products.groupdocs.app/conversion/stl-to-csv)