---
id: convert-webp-to-ppt
url: conversion/net/convert-webp-to-ppt
title: Convert WEBP to PPT
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (var converter = new GroupDocs.Conversion.Converter("sample.webp"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WEBP to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to PPT converter**](https://products.groupdocs.app/conversion/webp-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to PPT"](conversion/net/images/convert-to-ppt/convert-webp-to-ppt.png)](https://products.groupdocs.app/conversion/webp-to-ppt)