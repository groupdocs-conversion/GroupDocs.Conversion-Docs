---
id: jpm-to-svg
url: conversion/net/convert/jpm-to-svg
title: Convert JPM to SVG
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to SVG converter**](https://products.groupdocs.app/conversion/jpm-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to SVG"](conversion/net/images/convert-to-svg/convert-jpm-to-svg.png)](https://products.groupdocs.app/conversion/jpm-to-svg)