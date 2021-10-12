---
id: j2c-to-tex
url: conversion/net/convert/j2c-to-tex
title: Convert J2C to TEX
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2c"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2C to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to TEX converter**](https://products.groupdocs.app/conversion/j2c-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to TEX"](conversion/net/images/convert-to-tex/convert-j2c-to-tex.png)](https://products.groupdocs.app/conversion/j2c-to-tex)