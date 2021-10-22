---
id: jpg-to-ppt
url: conversion/net/convert/jpg-to-ppt
title: Convert JPG to PPT
description: "JPG format represents Joint Photographic Expert Group Image File with .jpg extension. Learn how to convert JPG to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPG to PPT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JPG to PPT in C#
    appDescription: Convert JPG to PPT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JPG to PPT in C# 
        description: Some description
        url: conversion/net/convert/jpg-to-ppt/#steps-to-convert-jpg-to-ppt-in-c
        steps:
        - name: Load source JPG file 
          text: Create an instance of Converter class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

## Steps to convert JPG to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPG file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPG to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**JPG to PPT converter**](https://products.groupdocs.app/conversion/jpg-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPG to PPT"](conversion/net/images/convert-to-ppt/convert-jpg-to-ppt.png)](https://products.groupdocs.app/conversion/jpg-to-ppt)