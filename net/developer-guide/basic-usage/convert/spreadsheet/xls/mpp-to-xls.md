---
id: mpp-to-xls
url: conversion/net/convert/mpp-to-xls
title: Convert MPP to XLS
description: "MPP format represents Microsoft Project File with .mpp extension. Learn how to convert MPP to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPP to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with MPP extension is Microsoft Project data file that stores information related to project management in an integrated manner. It is proprietary file format developed by Microsoft as file format for Microsoft Project (MSP) which is a project management application software. Besides MPP, MSP supports other file formats as well like project XML schema. Several APIs and applications provide the facility to convert MPP file format to others.

## Steps to convert MPP to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPP file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPP file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpp"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPP to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**MPP to XLS converter**](https://products.groupdocs.app/conversion/mpp-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPP to XLS"](conversion/net/images/convert-to-xls/convert-mpp-to-xls.png)](https://products.groupdocs.app/conversion/mpp-to-xls)