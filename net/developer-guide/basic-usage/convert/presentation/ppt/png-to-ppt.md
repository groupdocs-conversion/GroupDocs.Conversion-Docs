---
id: png-to-ppt
url: conversion/net/convert/png-to-ppt
title: Convert PNG to PPT
description: "PNG format represents Portable Network Graphic with .png extension. Learn how to convert PNG to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PNG to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PNG, Portable Network Graphics, refers to a type of raster image file format that use loseless compression. This file format was created as a replacement of Graphics Interchange Format (GIF) and has no copyright limitations. However, PNG file format does not support animations. PNG file format supports loseless image compression that makes it popular among its users. With the passage of time, PNG has evolved as one of the mostly used image file format.

## Steps to convert PNG to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PNG file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PNG to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**PNG to PPT converter**](https://products.groupdocs.app/conversion/png-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PNG to PPT"](conversion/net/images/convert-to-ppt/convert-png-to-ppt.png)](https://products.groupdocs.app/conversion/png-to-ppt)