---
id: convert-jpc-to-ppt
url: conversion/net/convert-jpc-to-ppt
title: Convert JPC to PPT
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to PPT converter**](https://products.groupdocs.app/conversion/jpc-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to PPT"](conversion/net/images/convert-to-ppt/convert-jpc-to-ppt.png)](https://products.groupdocs.app/conversion/jpc-to-ppt)