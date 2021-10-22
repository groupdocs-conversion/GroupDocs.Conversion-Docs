---
id: tif-to-doc
url: conversion/net/convert/tif-to-doc
title: Convert TIF to DOC
description: "TIF format represents Tagged Image File Format with .tif extension. Learn how to convert TIF to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TIF to DOC in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TIF to DOC in C#
    appDescription: Convert TIF to DOC natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TIF to DOC in C# 
        description: Some description
        url: conversion/net/convert/tif-to-doc/#steps-to-convert-tif-to-doc-in-c
        steps:
        - name: Load source TIF file 
          text: Create an instance of Converter class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOC and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

TIF or TIFF, Tagged Image File Format, represents raster images that are meant for usage on a variety of devices that comply with this file format standard. It is capable of describing bilevel, grayscale, palette-color and full-color image data in several color spaces. It supports lossy as well as lossless compression schemes to choose between space and time for applications using the format.

## Steps to convert TIF to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TIF file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TIF file
using (var converter = new GroupDocs.Conversion.Converter("sample.tif"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TIF to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**TIF to DOC converter**](https://products.groupdocs.app/conversion/tif-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TIF to DOC"](conversion/net/images/convert-to-doc/convert-tif-to-doc.png)](https://products.groupdocs.app/conversion/tif-to-doc)