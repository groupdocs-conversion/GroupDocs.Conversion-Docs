---
id: plt-to-doc
url: conversion/net/convert/plt-to-doc
title: Convert PLT to DOC
description: "PLT format represents PLT (HPGL) with .plt extension. Learn how to convert PLT to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PLT to DOC in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PLT to DOC in C#
    appDescription: Convert PLT to DOC natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PLT to DOC in C# 
        description: Quick guide about how to convert PLT to DOC in C# with high performance and accuracy.
        url: conversion/net/convert/plt-to-doc/#steps-to-convert-plt-to-doc-in-c
        steps:
        - name: Load source PLT file 
          text: Create an instance of Converter class and pass source PLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

An HPGL(Hewlett-Packard Graphics Language) file contains an instruction set for plotter control, developed by Hewlett-Packard. Hewlett-Packard plotters use this file to draw and print vector and raster content on the paper.

## Steps to convert PLT to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PLT file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.plt"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PLT to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**PLT to DOC converter**](https://products.groupdocs.app/conversion/plt-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PLT to DOC"](conversion/net/images/convert-to-doc/convert-plt-to-doc.png)](https://products.groupdocs.app/conversion/plt-to-doc)