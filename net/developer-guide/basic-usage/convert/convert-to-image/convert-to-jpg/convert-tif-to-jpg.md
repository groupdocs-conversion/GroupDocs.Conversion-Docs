---
id: convert-tif-to-jpg
url: conversion/net/convert-tif-to-jpg
title: Convert TIF to JPG
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TIF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (Converter converter = new Converter("sample.tif"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to JPG converter**](https://products.groupdocs.app/conversion/tif-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to JPG"](conversion/net/images/convert-to-jpg/convert-tif-to-jpg.png)](https://products.groupdocs.app/conversion/tif-to-jpg)