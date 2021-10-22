---
id: svgz-to-txt
url: conversion/net/convert/svgz-to-txt
title: Convert SVGZ to TXT
description: "SVGZ format represents Compressed Scalable Vector Graphics File with .svgz extension. Learn how to convert SVGZ to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVGZ to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert SVGZ to TXT in C#
    appDescription: Convert SVGZ to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert SVGZ to TXT in C# 
        description: Some description
        url: conversion/net/convert/svgz-to-txt/#steps-to-convert-svgz-to-txt-in-c
        steps:
        - name: Load source SVGZ file 
          text: Create an instance of Converter class and pass source SVGZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TXT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A file with .svgz extension is a compressed version of Scalable Vector Graphics (.SVG) file. It is compressed with gzip compression and contains data in XML format. SVGZ files support transparency, gradients, animations, and filters. SVGZ files are smaller in size as compared to the default SVG files and this reduced file size helps transfer the graphics files.

## Steps to convert SVGZ to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVGZ file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVGZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVGZ file
using (var converter = new GroupDocs.Conversion.Converter("sample.svgz"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVGZ to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**SVGZ to TXT converter**](https://products.groupdocs.app/conversion/svgz-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVGZ to TXT"](conversion/net/images/convert-to-txt/convert-svgz-to-txt.png)](https://products.groupdocs.app/conversion/svgz-to-txt)