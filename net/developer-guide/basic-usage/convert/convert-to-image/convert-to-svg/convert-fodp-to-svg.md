---
id: convert-fodp-to-svg
url: conversion/net/convert-fodp-to-svg
title: Convert FODP to SVG
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to SVG converter**](https://products.groupdocs.app/conversion/fodp-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to SVG"](conversion/net/images/convert-to-svg/convert-fodp-to-svg.png)](https://products.groupdocs.app/conversion/fodp-to-svg)