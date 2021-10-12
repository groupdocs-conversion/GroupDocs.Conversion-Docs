---
id: jls-to-svg
url: conversion/net/convert/jls-to-svg
title: Convert JLS to SVG
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

## Steps to convert JLS to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JLS file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.jls"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JLS to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to SVG converter**](https://products.groupdocs.app/conversion/jls-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to SVG"](conversion/net/images/convert-to-svg/convert-jls-to-svg.png)](https://products.groupdocs.app/conversion/jls-to-svg)