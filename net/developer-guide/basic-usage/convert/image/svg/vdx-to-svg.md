---
id: vdx-to-svg
url: conversion/net/convert/vdx-to-svg
title: Convert VDX to SVG
description: "VDX format represents Microsoft Visio XML Drawing File Format with .vdx extension. Learn how to convert VDX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDX to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Any drawing or chart created in Microsoft Visio, but saved in XML format has a VDX extension. A Visio drawing XML file is created in Visio software, which is developed by Microsoft. Microsoft Visio has the capability to generate visual documents that can be used in presentations and documents. The Visio drawing XML file contains the visual objects and metadata details of the visual elements.

## Steps to convert VDX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vdx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VDX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**VDX to SVG converter**](https://products.groupdocs.app/conversion/vdx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDX to SVG"](conversion/net/images/convert-to-svg/convert-vdx-to-svg.png)](https://products.groupdocs.app/conversion/vdx-to-svg)