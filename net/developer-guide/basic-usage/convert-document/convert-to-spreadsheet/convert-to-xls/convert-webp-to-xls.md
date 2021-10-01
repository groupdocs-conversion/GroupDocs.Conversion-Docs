---
id: convert-webp-to-xls
url: conversion/net/convert-webp-to-xls
title: Convert WEBP to XLS
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to XLS converter**](https://products.groupdocs.app/conversion/webp-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to XLS"](conversion/net/images/convert-to-xls/convert-webp-to-xls.png)](https://products.groupdocs.app/conversion/webp-to-xls)