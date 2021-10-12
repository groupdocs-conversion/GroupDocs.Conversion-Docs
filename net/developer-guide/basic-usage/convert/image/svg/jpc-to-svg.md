---
id: jpc-to-svg
url: conversion/net/convert/jpc-to-svg
title: Convert JPC to SVG
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to SVG converter**](https://products.groupdocs.app/conversion/jpc-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to SVG"](conversion/net/images/convert-to-svg/convert-jpc-to-svg.png)](https://products.groupdocs.app/conversion/jpc-to-svg)