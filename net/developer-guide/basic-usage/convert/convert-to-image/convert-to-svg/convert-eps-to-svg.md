---
id: convert-eps-to-svg
url: conversion/net/convert-eps-to-svg
title: Convert EPS to SVG
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to SVG converter**](https://products.groupdocs.app/conversion/eps-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to SVG"](conversion/net/images/convert-to-svg/convert-eps-to-svg.png)](https://products.groupdocs.app/conversion/eps-to-svg)