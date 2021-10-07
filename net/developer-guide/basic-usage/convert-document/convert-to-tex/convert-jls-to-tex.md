---
id: convert-jls-to-tex
url: conversion/net/convert-jls-to-tex
title: Convert JLS to TEX
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

## Steps to convert JLS to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JLS file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.jls"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JLS to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to TEX converter**](https://products.groupdocs.app/conversion/jls-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to TEX"](conversion/net/images/convert-to-tex/convert-jls-to-tex.png)](https://products.groupdocs.app/conversion/jls-to-tex)