---
id: convert-fods-to-ppt
url: conversion/net/convert-fods-to-ppt
title: Convert FODS to PPT
description: "FODS format represents OpenDocument Flat XML Spreadsheet with .fods extension. Learn how to convert FODS to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODS to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODS is a ZIP-compressed XML-based file format for spreadsheets, charts, presentations, and word processing documents.

## Steps to convert FODS to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODS file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODS file
using (var converter = new GroupDocs.Conversion.Converter("sample.fods"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODS to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**FODS to PPT converter**](https://products.groupdocs.app/conversion/fods-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODS to PPT"](conversion/net/images/convert-to-ppt/convert-fods-to-ppt.png)](https://products.groupdocs.app/conversion/fods-to-ppt)