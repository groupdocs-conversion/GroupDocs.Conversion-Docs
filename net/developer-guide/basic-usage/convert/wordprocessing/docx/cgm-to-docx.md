---
id: cgm-to-docx
url: conversion/net/convert/cgm-to-docx
title: Convert CGM to DOCX
description: "CGM format represents Computer Graphics Metafile with .cgm extension. Learn how to convert CGM to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CGM to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CGM to DOCX in C#
    appDescription: Convert CGM to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CGM to DOCX in C# 
        description: Some description
        url: conversion/net/convert/cgm-to-docx/#steps-to-convert-cgm-to-docx-in-c
        steps:
        - name: Load source CGM file 
          text: Create an instance of Converter class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Computer Graphics Metafile (CGM) is free, platform-independent, international standard metafile format for storing and exchanging vector graphics (2D), raster graphics, and text. CGM uses an object-oriented approach and many function provisions for image production. CGM uses these object-oriented characteristics for remolding graphical elements to render an image. A metafile contains necessary information that defines other files. In CGM, a text-based source file contains all graphical elements that can be later compiled into a binary file.

## Steps to convert CGM to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CGM file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CGM file
using (var converter = new GroupDocs.Conversion.Converter("sample.cgm"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CGM to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**CGM to DOCX converter**](https://products.groupdocs.app/conversion/cgm-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CGM to DOCX"](conversion/net/images/convert-to-docx/convert-cgm-to-docx.png)](https://products.groupdocs.app/conversion/cgm-to-docx)