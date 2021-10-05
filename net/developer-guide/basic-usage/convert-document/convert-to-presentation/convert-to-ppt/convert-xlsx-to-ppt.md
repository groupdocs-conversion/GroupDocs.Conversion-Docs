---
id: convert-xlsx-to-ppt
url: conversion/net/convert-xlsx-to-ppt
title: Convert XLSX to PPT
description: "XLSX format represents Microsoft Excel Open XML Spreadsheet with .xlsx extension. Learn how to convert XLSX to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSX to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

## Steps to convert XLSX to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSX file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSX to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSX to PPT converter**](https://products.groupdocs.app/conversion/xlsx-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSX to PPT"](conversion/net/images/convert-to-ppt/convert-xlsx-to-ppt.png)](https://products.groupdocs.app/conversion/xlsx-to-ppt)