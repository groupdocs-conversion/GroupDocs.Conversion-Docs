---
id: webp-to-txt
url: conversion/net/convert/webp-to-txt
title: Convert WEBP to TXT
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to TXT converter**](https://products.groupdocs.app/conversion/webp-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to TXT"](conversion/net/images/convert-to-txt/convert-webp-to-txt.png)](https://products.groupdocs.app/conversion/webp-to-txt)