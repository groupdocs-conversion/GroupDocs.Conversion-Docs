---
id: gif-to-ppt
url: conversion/net/convert/gif-to-ppt
title: Convert GIF to PPT
description: "GIF format represents Graphical Interchange Format File with .gif extension. Learn how to convert GIF to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert GIF to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A GIF or Graphical Interchange Format is a type of highly compressed image. Owned by Unisys, GIF uses the LZW compression algorithm that does not degrade the image quality. For each image GIF typically allow up to 8 bits per pixel and up to 256 colors are allowed across the image. In contrast to a JPEG image, which can display up to 16 million colors and fairly touches the limits of the human eye.

## Steps to convert GIF to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the GIF file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source GIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source GIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.gif"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### GIF to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**GIF to PPT converter**](https://products.groupdocs.app/conversion/gif-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert GIF to PPT"](conversion/net/images/convert-to-ppt/convert-gif-to-ppt.png)](https://products.groupdocs.app/conversion/gif-to-ppt)