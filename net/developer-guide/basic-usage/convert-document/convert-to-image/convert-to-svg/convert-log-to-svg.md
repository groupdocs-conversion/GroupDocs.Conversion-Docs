---
id: convert-log-to-svg
url: conversion/net/convert-log-to-svg
title: Convert LOG to SVG
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to SVG converter**](https://products.groupdocs.app/conversion/log-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to SVG"](conversion/net/images/convert-to-svg/convert-log-to-svg.png)](https://products.groupdocs.app/conversion/log-to-svg)