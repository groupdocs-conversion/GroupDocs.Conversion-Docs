---
id: webp-to-xlsx
url: conversion/net/convert/webp-to-xlsx
title: Convert WEBP to XLSX
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to XLSX converter**](https://products.groupdocs.app/conversion/webp-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to XLSX"](conversion/net/images/convert-to-xlsx/convert-webp-to-xlsx.png)](https://products.groupdocs.app/conversion/webp-to-xlsx)