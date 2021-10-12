---
id: tsv-to-ppt
url: conversion/net/convert/tsv-to-ppt
title: Convert TSV to PPT
description: "TSV format represents Tab Separated Values File with .tsv extension. Learn how to convert TSV to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TSV to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

## Steps to convert TSV to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TSV file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.tsv"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TSV to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to PPT converter**](https://products.groupdocs.app/conversion/tsv-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to PPT"](conversion/net/images/convert-to-ppt/convert-tsv-to-ppt.png)](https://products.groupdocs.app/conversion/tsv-to-ppt)