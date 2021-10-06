---
id: convert-dib-to-jpg
url: conversion/net/convert-dib-to-jpg
title: Convert DIB to JPG
description: "DIB format represents Device Independent Bitmap File with .dib extension. Learn how to convert DIB to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DIB to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Device-Independent bitmap (DIB) is a raster image file that is similar in structure to the standard Bitmap files(BMP). It contains a color table that describes the mapping of RGB colors to the pixel values. This enables DIB to represent images on any device. It can be opened with almost all applications that can open a standard BMP file on Windows as well as macOS.

## Steps to convert DIB to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DIB file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DIB document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DIB file
using (Converter converter = new Converter("sample.dib"))
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

### DIB to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DIB to JPG converter**](https://products.groupdocs.app/conversion/dib-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DIB to JPG"](conversion/net/images/convert-to-jpg/convert-dib-to-jpg.png)](https://products.groupdocs.app/conversion/dib-to-jpg)