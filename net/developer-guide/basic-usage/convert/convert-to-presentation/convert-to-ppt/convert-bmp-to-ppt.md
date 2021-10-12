---
id: convert-bmp-to-ppt
url: conversion/net/convert-bmp-to-ppt
title: Convert BMP to PPT
description: "BMP format represents Bitmap File Format with .bmp extension. Learn how to convert BMP to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert BMP to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files having extension .BMP represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images  in both monochrome as well as color format with various colour depths.

## Steps to convert BMP to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the BMP file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source BMP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source BMP file
using (var converter = new GroupDocs.Conversion.Converter("sample.bmp"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### BMP to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**BMP to PPT converter**](https://products.groupdocs.app/conversion/bmp-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert BMP to PPT"](conversion/net/images/convert-to-ppt/convert-bmp-to-ppt.png)](https://products.groupdocs.app/conversion/bmp-to-ppt)