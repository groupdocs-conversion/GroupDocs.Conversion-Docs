---
id: dwfx-to-xls
url: conversion/net/convert/dwfx-to-xls
title: Convert DWFX to XLS
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwfx"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWFX to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to XLS converter**](https://products.groupdocs.app/conversion/dwfx-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to XLS"](conversion/net/images/convert-to-xls/convert-dwfx-to-xls.png)](https://products.groupdocs.app/conversion/dwfx-to-xls)