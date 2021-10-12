---
id: mpx-to-svg
url: conversion/net/convert/mpx-to-svg
title: Convert MPX to SVG
description: "MPX format represents Microsoft Project Exchange File with .mpx extension. Learn how to convert MPX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPX to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MPX, Microsoft Exchange File Format, is an ASCII file format for transferring project information between Microsoft Project (MSP) and other applications that support the MPX file format such as Primavera Project Planner, Sciforma, and Timberline Precision Estimating. The MPX file format allows you to transfer project information that cannot appear in a table, such as detailed resource assignment information, calendar information, or information in the Project Info dialog box.

## Steps to convert MPX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**MPX to SVG converter**](https://products.groupdocs.app/conversion/mpx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPX to SVG"](conversion/net/images/convert-to-svg/convert-mpx-to-svg.png)](https://products.groupdocs.app/conversion/mpx-to-svg)