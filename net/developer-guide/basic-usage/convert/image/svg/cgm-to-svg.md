---
id: cgm-to-svg
url: conversion/net/convert/cgm-to-svg
title: Convert CGM to SVG
description: "CGM format represents Computer Graphics Metafile with .cgm extension. Learn how to convert CGM to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CGM to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Computer Graphics Metafile (CGM) is free, platform-independent, international standard metafile format for storing and exchanging vector graphics (2D), raster graphics, and text. CGM uses an object-oriented approach and many function provisions for image production. CGM uses these object-oriented characteristics for remolding graphical elements to render an image. A metafile contains necessary information that defines other files. In CGM, a text-based source file contains all graphical elements that can be later compiled into a binary file.

## Steps to convert CGM to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CGM file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CGM file
using (var converter = new GroupDocs.Conversion.Converter("sample.cgm"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CGM to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**CGM to SVG converter**](https://products.groupdocs.app/conversion/cgm-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CGM to SVG"](conversion/net/images/convert-to-svg/convert-cgm-to-svg.png)](https://products.groupdocs.app/conversion/cgm-to-svg)