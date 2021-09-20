---
id: convert-igs-to-pdf
url: conversion/net/convert-igs-to-pdf
title: Convert IGS to PDF
description: "IGS files can be accurately and precisely converted to PDF document using C# language. Check simple code snippet to know how to convert IGS to PDF using Groupdocs.Conversion for .NET library."
keywords: Convert IGS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .igs (Initial Graphics Exchange) extension is a 2D-3D design exchange file format that is independent of source or destination file format specifications used by CAD applications. It is be used to exchange design information about circuit diagrams, wireframe, freeform surface between two independent systems. It is similar to IGES and is primary requirement of manufacturers for pricing and designing molds for your product. IGS has most recently been replaced by the newer STEP(.STP) file format. IGS files can be opened by applications such as Autodesk, FreeCAD, CADEX CAD Exchanger and other similar applications.

To convert IGS to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source IGS file
using (Converter converter = new Converter("sample.igs"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**IGS to PDF converter**](https://products.groupdocs.app/conversion/igs-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IGS to PDF"](conversion/net/images/convert-igs-to-pdf.png)](https://products.groupdocs.app/conversion/igs-to-pdf)