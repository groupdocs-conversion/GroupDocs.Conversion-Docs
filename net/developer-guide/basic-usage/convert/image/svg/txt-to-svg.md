---
id: txt-to-svg
url: conversion/net/convert/txt-to-svg
title: Convert TXT to SVG
description: "TXT format represents Plain Text File Format with .txt extension. Learn how to convert TXT to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TXT to SVG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TXT to SVG in C#
    appDescription: Convert TXT to SVG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TXT to SVG in C# 
        description: Some description
        url: conversion/net/convert/txt-to-svg/#steps-to-convert-txt-to-svg-in-c
        steps:
        - name: Load source TXT file 
          text: Create an instance of Converter class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

## Steps to convert TXT to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TXT file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TXT file
using (var converter = new GroupDocs.Conversion.Converter("sample.txt"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TXT to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**TXT to SVG converter**](https://products.groupdocs.app/conversion/txt-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TXT to SVG"](conversion/net/images/convert-to-svg/convert-txt-to-svg.png)](https://products.groupdocs.app/conversion/txt-to-svg)