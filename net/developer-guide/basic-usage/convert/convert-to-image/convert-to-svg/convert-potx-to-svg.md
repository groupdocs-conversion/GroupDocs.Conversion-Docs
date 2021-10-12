---
id: convert-potx-to-svg
url: conversion/net/convert-potx-to-svg
title: Convert POTX to SVG
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

## Steps to convert POTX to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTX file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.potx"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTX to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to SVG converter**](https://products.groupdocs.app/conversion/potx-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to SVG"](conversion/net/images/convert-to-svg/convert-potx-to-svg.png)](https://products.groupdocs.app/conversion/potx-to-svg)