---
id: vtx-to-xls
url: conversion/net/convert/vtx-to-xls
title: Convert VTX to XLS
description: "VTX format represents Microsoft Visio Drawing Template with .vtx extension. Learn how to convert VTX to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VTX to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

## Steps to convert VTX to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VTX file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vtx"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VTX to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**VTX to XLS converter**](https://products.groupdocs.app/conversion/vtx-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VTX to XLS"](conversion/net/images/convert-to-xls/convert-vtx-to-xls.png)](https://products.groupdocs.app/conversion/vtx-to-xls)