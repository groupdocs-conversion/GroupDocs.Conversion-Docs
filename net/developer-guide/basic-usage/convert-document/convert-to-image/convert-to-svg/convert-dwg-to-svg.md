---
id: convert-dwg-to-svg
url: conversion/net/convert-dwg-to-svg
title: Convert DWG to SVG
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to SVG converter**](https://products.groupdocs.app/conversion/dwg-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to SVG"](conversion/net/images/convert-to-svg/convert-dwg-to-svg.png)](https://products.groupdocs.app/conversion/dwg-to-svg)