---
id: convert-gif-to-jpg
url: conversion/net/convert-gif-to-jpg
title: Convert GIF to JPG
description: "GIF format represents Graphical Interchange Format File with .gif extension. Learn how to convert GIF to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert GIF to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A GIF or Graphical Interchange Format is a type of highly compressed image. Owned by Unisys, GIF uses the LZW compression algorithm that does not degrade the image quality. For each image GIF typically allow up to 8 bits per pixel and up to 256 colors are allowed across the image. In contrast to a JPEG image, which can display up to 16 million colors and fairly touches the limits of the human eye.

## Steps to convert GIF to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the GIF file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source GIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source GIF file
using (Converter converter = new Converter("sample.gif"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### GIF to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**GIF to JPG converter**](https://products.groupdocs.app/conversion/gif-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert GIF to JPG"](conversion/net/images/convert-to-jpg/convert-gif-to-jpg.png)](https://products.groupdocs.app/conversion/gif-to-jpg)