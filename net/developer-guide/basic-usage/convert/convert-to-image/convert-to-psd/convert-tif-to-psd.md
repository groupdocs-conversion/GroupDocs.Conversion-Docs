---
id: convert-tif-to-psd
url: conversion/net/convert-tif-to-psd
title: Convert TIF to PSD
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TIF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (Converter converter = new Converter("sample.tif"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to PSD converter**](https://products.groupdocs.app/conversion/tif-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to PSD"](conversion/net/images/convert-to-psd/convert-tif-to-psd.png)](https://products.groupdocs.app/conversion/tif-to-psd)