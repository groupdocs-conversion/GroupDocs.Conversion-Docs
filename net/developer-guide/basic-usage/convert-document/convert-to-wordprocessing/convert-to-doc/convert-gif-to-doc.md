---
id: convert-gif-to-doc
url: conversion/net/convert-gif-to-doc
title: Convert GIF to DOC
description: "GIF format represents Graphical Interchange Format File with .gif extension. Learn how to convert GIF to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert GIF to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A GIF or Graphical Interchange Format is a type of highly compressed image. Owned by Unisys, GIF uses the LZW compression algorithm that does not degrade the image quality. For each image GIF typically allow up to 8 bits per pixel and up to 256 colors are allowed across the image. In contrast to a JPEG image, which can display up to 16 million colors and fairly touches the limits of the human eye.

## Steps to convert GIF to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the GIF file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source GIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source GIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.gif"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### GIF to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**GIF to DOC converter**](https://products.groupdocs.app/conversion/gif-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert GIF to DOC"](conversion/net/images/convert-to-doc/convert-gif-to-doc.png)](https://products.groupdocs.app/conversion/gif-to-doc)