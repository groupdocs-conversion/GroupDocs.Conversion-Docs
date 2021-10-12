---
id: convert-igs-to-pptx
url: conversion/net/convert-igs-to-pptx
title: Convert IGS to PPTX
description: "IGS format represents Initial Graphics Exchange Specification (IGES) with .igs extension. Learn how to convert IGS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IGS to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .igs (Initial Graphics Exchange) extension is a 2D-3D design exchange file format that is independent of source or destination file format specifications used by CAD applications. It is used to exchange design information about circuit diagrams, wireframes, the freeform surfaces between two independent systems. IGS files can be opened by applications such as Autodesk, FreeCAD, CADEX CAD Exchanger, and other similar applications.

## Steps to convert IGS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IGS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IGS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IGS file
using (var converter = new GroupDocs.Conversion.Converter("sample.igs"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### IGS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**IGS to PPTX converter**](https://products.groupdocs.app/conversion/igs-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IGS to PPTX"](conversion/net/images/convert-to-pptx/convert-igs-to-pptx.png)](https://products.groupdocs.app/conversion/igs-to-pptx)