---
id: svgz-to-tex
url: conversion/net/convert/svgz-to-tex
title: Convert SVGZ to TEX
description: "SVGZ format represents Compressed Scalable Vector Graphics File with .svgz extension. Learn how to convert SVGZ to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVGZ to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .svgz extension is a compressed version of Scalable Vector Graphics (.SVG) file. It is compressed with gzip compression and contains data in XML format. SVGZ files support transparency, gradients, animations, and filters. SVGZ files are smaller in size as compared to the default SVG files and this reduced file size helps transfer the graphics files.

## Steps to convert SVGZ to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVGZ file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVGZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVGZ file
using (var converter = new GroupDocs.Conversion.Converter("sample.svgz"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVGZ to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**SVGZ to TEX converter**](https://products.groupdocs.app/conversion/svgz-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVGZ to TEX"](conversion/net/images/convert-to-tex/convert-svgz-to-tex.png)](https://products.groupdocs.app/conversion/svgz-to-tex)