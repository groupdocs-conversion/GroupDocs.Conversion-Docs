---
id: convert-dib-to-xls
url: conversion/net/convert-dib-to-xls
title: Convert DIB to XLS
description: "DIB format represents Device Independent Bitmap File with .dib extension. Learn how to convert DIB to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DIB to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Device-Independent bitmap (DIB) is a raster image file that is similar in structure to the standard Bitmap files(BMP). It contains a color table that describes the mapping of RGB colors to the pixel values. This enables DIB to represent images on any device. It can be opened with almost all applications that can open a standard BMP file on Windows as well as macOS.

## Steps to convert DIB to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DIB file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DIB file
using (var converter = new GroupDocs.Conversion.Converter("sample.dib"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DIB to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**DIB to XLS converter**](https://products.groupdocs.app/conversion/dib-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DIB to XLS"](conversion/net/images/convert-to-xls/convert-dib-to-xls.png)](https://products.groupdocs.app/conversion/dib-to-xls)