---
id: convert-tiff-to-png
url: conversion/net/convert-tiff-to-png
title: Convert TIFF to PNG
description: "TIFF format represents Tagged Image File Format with .tiff extension. Learn how to convert TIFF to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIFF to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIFF or TIF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIFF to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIFF file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIFF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TIFF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIFF file
using (Converter converter = new Converter("sample.tiff"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIFF to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**TIFF to PNG converter**](https://products.groupdocs.app/conversion/tiff-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIFF to PNG"](conversion/net/images/convert-to-png/convert-tiff-to-png.png)](https://products.groupdocs.app/conversion/tiff-to-png)