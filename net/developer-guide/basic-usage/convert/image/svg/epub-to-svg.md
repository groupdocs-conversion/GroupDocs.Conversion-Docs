---
id: epub-to-svg
url: conversion/net/convert/epub-to-svg
title: Convert EPUB to SVG
description: "EPUB format represents Digital E-Book File Format with .epub extension. Learn how to convert EPUB to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPUB to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

## Steps to convert EPUB to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPUB file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPUB file
using (var converter = new GroupDocs.Conversion.Converter("sample.epub"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPUB to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPUB to SVG converter**](https://products.groupdocs.app/conversion/epub-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPUB to SVG"](conversion/net/images/convert-to-svg/convert-epub-to-svg.png)](https://products.groupdocs.app/conversion/epub-to-svg)