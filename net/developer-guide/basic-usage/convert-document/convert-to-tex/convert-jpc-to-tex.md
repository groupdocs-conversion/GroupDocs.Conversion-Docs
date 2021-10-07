---
id: convert-jpc-to-tex
url: conversion/net/convert-jpc-to-tex
title: Convert JPC to TEX
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to TEX converter**](https://products.groupdocs.app/conversion/jpc-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to TEX"](conversion/net/images/convert-to-tex/convert-jpc-to-tex.png)](https://products.groupdocs.app/conversion/jpc-to-tex)