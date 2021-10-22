---
id: cgm-to-tex
url: conversion/net/convert/cgm-to-tex
title: Convert CGM to TEX
description: "CGM format represents Computer Graphics Metafile with .cgm extension. Learn how to convert CGM to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CGM to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CGM to TEX in C#
    appDescription: Convert CGM to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CGM to TEX in C# 
        description: Some description
        url: conversion/net/convert/cgm-to-tex/#steps-to-convert-cgm-to-tex-in-c
        steps:
        - name: Load source CGM file 
          text: Create an instance of Converter class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TEX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Computer Graphics Metafile (CGM) is free, platform-independent, international standard metafile format for storing and exchanging vector graphics (2D), raster graphics, and text. CGM uses an object-oriented approach and many function provisions for image production. CGM uses these object-oriented characteristics for remolding graphical elements to render an image. A metafile contains necessary information that defines other files. In CGM, a text-based source file contains all graphical elements that can be later compiled into a binary file.

## Steps to convert CGM to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CGM file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CGM file
using (var converter = new GroupDocs.Conversion.Converter("sample.cgm"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CGM to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**CGM to TEX converter**](https://products.groupdocs.app/conversion/cgm-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CGM to TEX"](conversion/net/images/convert-to-tex/convert-cgm-to-tex.png)](https://products.groupdocs.app/conversion/cgm-to-tex)