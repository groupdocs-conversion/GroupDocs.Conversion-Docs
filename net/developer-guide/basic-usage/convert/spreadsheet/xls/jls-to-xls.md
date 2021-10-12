---
id: jls-to-xls
url: conversion/net/convert/jls-to-xls
title: Convert JLS to XLS
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

## Steps to convert JLS to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JLS file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.jls"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JLS to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to XLS converter**](https://products.groupdocs.app/conversion/jls-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to XLS"](conversion/net/images/convert-to-xls/convert-jls-to-xls.png)](https://products.groupdocs.app/conversion/jls-to-xls)