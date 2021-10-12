---
id: convert-bmp-to-doc
url: conversion/net/convert-bmp-to-doc
title: Convert BMP to DOC
description: "BMP format represents Bitmap File Format with .bmp extension. Learn how to convert BMP to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert BMP to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files having extension .BMP represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images  in both monochrome as well as color format with various colour depths.

## Steps to convert BMP to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the BMP file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source BMP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source BMP file
using (var converter = new GroupDocs.Conversion.Converter("sample.bmp"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### BMP to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**BMP to DOC converter**](https://products.groupdocs.app/conversion/bmp-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert BMP to DOC"](conversion/net/images/convert-to-doc/convert-bmp-to-doc.png)](https://products.groupdocs.app/conversion/bmp-to-doc)