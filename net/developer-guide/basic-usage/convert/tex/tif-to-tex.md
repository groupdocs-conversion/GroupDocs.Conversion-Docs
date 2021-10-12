---
id: tif-to-tex
url: conversion/net/convert/tif-to-tex
title: Convert TIF to TEX
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tif"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to TEX converter**](https://products.groupdocs.app/conversion/tif-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to TEX"](conversion/net/images/convert-to-tex/convert-tif-to-tex.png)](https://products.groupdocs.app/conversion/tif-to-tex)