---
id: igs-to-tex
url: conversion/net/convert/igs-to-tex
title: Convert IGS to TEX
description: "IGS format represents Initial Graphics Exchange Specification (IGES) with .igs extension. Learn how to convert IGS to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IGS to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .igs (Initial Graphics Exchange) extension is a 2D-3D design exchange file format that is independent of source or destination file format specifications used by CAD applications. It is used to exchange design information about circuit diagrams, wireframes, the freeform surfaces between two independent systems. IGS files can be opened by applications such as Autodesk, FreeCAD, CADEX CAD Exchanger, and other similar applications.

## Steps to convert IGS to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IGS file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IGS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IGS file
using (var converter = new GroupDocs.Conversion.Converter("sample.igs"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### IGS to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**IGS to TEX converter**](https://products.groupdocs.app/conversion/igs-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IGS to TEX"](conversion/net/images/convert-to-tex/convert-igs-to-tex.png)](https://products.groupdocs.app/conversion/igs-to-tex)