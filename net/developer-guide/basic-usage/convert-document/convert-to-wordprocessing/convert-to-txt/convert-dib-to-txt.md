---
id: convert-dib-to-txt
url: conversion/net/convert-dib-to-txt
title: Convert DIB to TXT
description: "DIB format represents Device Independent Bitmap File with .dib extension. Learn how to convert DIB to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DIB to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Device-Independent bitmap (DIB) is a raster image file that is similar in structure to the standard Bitmap files(BMP). It contains a color table that describes the mapping of RGB colors to the pixel values. This enables DIB to represent images on any device. It can be opened with almost all applications that can open a standard BMP file on Windows as well as macOS.

## Steps to convert DIB to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DIB file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DIB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DIB file
using (var converter = new GroupDocs.Conversion.Converter("sample.dib"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DIB to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DIB to TXT converter**](https://products.groupdocs.app/conversion/dib-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DIB to TXT"](conversion/net/images/convert-to-txt/convert-dib-to-txt.png)](https://products.groupdocs.app/conversion/dib-to-txt)