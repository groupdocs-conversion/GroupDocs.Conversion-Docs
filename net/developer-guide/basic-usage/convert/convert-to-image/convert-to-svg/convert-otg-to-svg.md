---
id: convert-otg-to-svg
url: conversion/net/convert-otg-to-svg
title: Convert OTG to SVG
description: "OTG format represents OpenDocument Graphic Template with .otg extension. Learn how to convert OTG to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTG to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An OTG file is a drawing template that is created using the OpenDocument standard that follows the OASIS Office Applications 1.0 specification. It represents the default organization of drawing elements for a vector image that can be used to further enhance the contents of the file.

## Steps to convert OTG to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTG file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTG file
using (var converter = new GroupDocs.Conversion.Converter("sample.otg"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTG to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**OTG to SVG converter**](https://products.groupdocs.app/conversion/otg-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTG to SVG"](conversion/net/images/convert-to-svg/convert-otg-to-svg.png)](https://products.groupdocs.app/conversion/otg-to-svg)