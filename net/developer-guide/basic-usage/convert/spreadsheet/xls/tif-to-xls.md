---
id: tif-to-xls
url: conversion/net/convert/tif-to-xls
title: Convert TIF to XLS
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tif"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to XLS converter**](https://products.groupdocs.app/conversion/tif-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to XLS"](conversion/net/images/convert-to-xls/convert-tif-to-xls.png)](https://products.groupdocs.app/conversion/tif-to-xls)