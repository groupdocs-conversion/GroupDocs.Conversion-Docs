---
id: convert-tif-to-txt
url: conversion/net/convert-tif-to-txt
title: Convert TIF to TXT
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tif"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to TXT converter**](https://products.groupdocs.app/conversion/tif-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to TXT"](conversion/net/images/convert-to-txt/convert-tif-to-txt.png)](https://products.groupdocs.app/conversion/tif-to-txt)