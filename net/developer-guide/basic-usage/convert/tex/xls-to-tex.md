---
id: xls-to-tex
url: conversion/net/convert/xls-to-tex
title: Convert XLS to TEX
description: "XLS format represents Microsoft Excel Binary File Format with .xls extension. Learn how to convert XLS to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLS to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

## Steps to convert XLS to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLS file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xls"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLS to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLS to TEX converter**](https://products.groupdocs.app/conversion/xls-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLS to TEX"](conversion/net/images/convert-to-tex/convert-xls-to-tex.png)](https://products.groupdocs.app/conversion/xls-to-tex)