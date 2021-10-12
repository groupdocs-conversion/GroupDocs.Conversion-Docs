---
id: convert-tiff-to-svg
url: conversion/net/convert-tiff-to-svg
title: Convert TIFF to SVG
description: "TIFF format represents Tagged Image File Format with .tiff extension. Learn how to convert TIFF to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIFF to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIFF or TIF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIFF to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIFF file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIFF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIFF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tiff"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIFF to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**TIFF to SVG converter**](https://products.groupdocs.app/conversion/tiff-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIFF to SVG"](conversion/net/images/convert-to-svg/convert-tiff-to-svg.png)](https://products.groupdocs.app/conversion/tiff-to-svg)