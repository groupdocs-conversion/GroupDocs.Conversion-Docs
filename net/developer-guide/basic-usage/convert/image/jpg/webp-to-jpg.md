---
id: webp-to-jpg
url: conversion/net/convert/webp-to-jpg
title: Convert WEBP to JPG
description: "WEBP format represents Raster Web Image File Format with .webp extension. Learn how to convert WEBP to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WEBP to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

WebP, introduced by Google, is a modern raster web image file format that is based on lossless and lossy compression. It provides same image quality while considerably reducing the image size. Since most of the web pages use images as effective representation of data, the use of WebP images in web pages results in faster loading of web pages.

## Steps to convert WEBP to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WEBP file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WEBP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of WEBP document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WEBP file
using (Converter converter = new Converter("sample.webp"))
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

### WEBP to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**WEBP to JPG converter**](https://products.groupdocs.app/conversion/webp-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WEBP to JPG"](conversion/net/images/convert-to-jpg/convert-webp-to-jpg.png)](https://products.groupdocs.app/conversion/webp-to-jpg)