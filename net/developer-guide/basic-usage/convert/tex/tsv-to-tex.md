---
id: tsv-to-tex
url: conversion/net/convert/tsv-to-tex
title: Convert TSV to TEX
description: "TSV format represents Tab Separated Values File with .tsv extension. Learn how to convert TSV to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TSV to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

## Steps to convert TSV to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TSV file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.tsv"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TSV to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to TEX converter**](https://products.groupdocs.app/conversion/tsv-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to TEX"](conversion/net/images/convert-to-tex/convert-tsv-to-tex.png)](https://products.groupdocs.app/conversion/tsv-to-tex)