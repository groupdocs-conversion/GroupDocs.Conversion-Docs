---
id: jpg-to-xlsx
url: conversion/net/convert/jpg-to-xlsx
title: Convert JPG to XLSX
description: "JPG format represents Joint Photographic Expert Group Image File with .jpg extension. Learn how to convert JPG to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPG to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

## Steps to convert JPG to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPG file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPG to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPG to XLSX converter**](https://products.groupdocs.app/conversion/jpg-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPG to XLSX"](conversion/net/images/convert-to-xlsx/convert-jpg-to-xlsx.png)](https://products.groupdocs.app/conversion/jpg-to-xlsx)