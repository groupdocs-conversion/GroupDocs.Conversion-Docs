---
id: jpg-to-svg
url: conversion/net/convert/jpg-to-svg
title: Convert JPG to SVG
description: "JPG format represents Joint Photographic Expert Group Image File with .jpg extension. Learn how to convert JPG to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPG to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

## Steps to convert JPG to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPG file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPG to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPG to SVG converter**](https://products.groupdocs.app/conversion/jpg-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPG to SVG"](conversion/net/images/convert-to-svg/convert-jpg-to-svg.png)](https://products.groupdocs.app/conversion/jpg-to-svg)