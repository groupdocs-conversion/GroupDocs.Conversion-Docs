---
id: tsv-to-svg
url: conversion/net/convert/tsv-to-svg
title: Convert TSV to SVG
description: "TSV format represents Tab Separated Values File with .tsv extension. Learn how to convert TSV to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TSV to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TSV to SVG in C#
    appDescription: Convert TSV to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TSV to SVG in C# 
        description: Some description
        url: conversion/net/convert/tsv-to-svg/#steps-to-convert-tsv-to-svg-in-c
        steps:
        - name: Load source TSV file 
          text: Create an instance of Converter class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to SVG and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

## Steps to convert TSV to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TSV file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.tsv"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TSV to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to SVG converter**](https://products.groupdocs.app/conversion/tsv-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to SVG"](conversion/net/images/convert-to-svg/convert-tsv-to-svg.png)](https://products.groupdocs.app/conversion/tsv-to-svg)