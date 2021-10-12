---
id: j2k-to-ppt
url: conversion/net/convert/j2k-to-ppt
title: Convert J2K to PPT
description: "J2K format represents JPEG 2000 Image with .j2k extension. Learn how to convert J2K to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2K to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2K file is an image that is compressed using the wavelet compression instead of DCT compression.

## Steps to convert J2K to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2K file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2K file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2K file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2k"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2K to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**J2K to PPT converter**](https://products.groupdocs.app/conversion/j2k-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2K to PPT"](conversion/net/images/convert-to-ppt/convert-j2k-to-ppt.png)](https://products.groupdocs.app/conversion/j2k-to-ppt)