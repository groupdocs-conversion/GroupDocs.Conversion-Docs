---
id: convert-dwg-to-xls
url: conversion/net/convert-dwg-to-xls
title: Convert DWG to XLS
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to XLS converter**](https://products.groupdocs.app/conversion/dwg-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to XLS"](conversion/net/images/convert-to-xls/convert-dwg-to-xls.png)](https://products.groupdocs.app/conversion/dwg-to-xls)