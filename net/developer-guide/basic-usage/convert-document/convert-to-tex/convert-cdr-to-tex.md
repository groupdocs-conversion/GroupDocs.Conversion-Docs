---
id: convert-cdr-to-tex
url: conversion/net/convert-cdr-to-tex
title: Convert CDR to TEX
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

## Steps to convert CDR to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CDR file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CDR file
using (var converter = new GroupDocs.Conversion.Converter("sample.cdr"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CDR to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to TEX converter**](https://products.groupdocs.app/conversion/cdr-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to TEX"](conversion/net/images/convert-to-tex/convert-cdr-to-tex.png)](https://products.groupdocs.app/conversion/cdr-to-tex)