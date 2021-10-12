---
id: rtf-to-svg
url: conversion/net/convert/rtf-to-svg
title: Convert RTF to SVG
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source RTF file
using (var converter = new GroupDocs.Conversion.Converter("sample.rtf"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to SVG converter**](https://products.groupdocs.app/conversion/rtf-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to SVG"](conversion/net/images/convert-to-svg/convert-rtf-to-svg.png)](https://products.groupdocs.app/conversion/rtf-to-svg)