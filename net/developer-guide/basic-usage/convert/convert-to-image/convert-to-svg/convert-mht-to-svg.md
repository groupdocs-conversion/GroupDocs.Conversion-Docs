---
id: convert-mht-to-svg
url: conversion/net/convert-mht-to-svg
title: Convert MHT to SVG
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mht"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHT to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to SVG converter**](https://products.groupdocs.app/conversion/mht-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to SVG"](conversion/net/images/convert-to-svg/convert-mht-to-svg.png)](https://products.groupdocs.app/conversion/mht-to-svg)