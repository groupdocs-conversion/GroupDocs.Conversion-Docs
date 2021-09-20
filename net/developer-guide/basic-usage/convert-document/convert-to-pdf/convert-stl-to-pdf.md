---
id: convert-stl-to-pdf
url: conversion/net/convert-stl-to-pdf
title: Convert STL to PDF
description: "This guide explains how to convert stereolithography STL file to PDF document using C# and GroupDocs.Conversion for .NET library."
keywords: Convert STL to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

STL, abbreviation for stereolithography, is an interchangeable file format that represents 3-dimensional surface geometry. The file format finds its usage in several fields such as rapid prototyping, 3D printing and computer-aided manufacturing. It represents a surface as a series of small triangles, known as facets, where each facet is described by a perpendicular direction and three points representing the vertices of the triangle. Resultant data is used by applications to determine the cross section of the 3D shape to be built by the fabber. There is no information available in the STL file format for representation of colour, texture or other common CAD model attributes.

To convert STL to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source STL file
using (Converter converter = new Converter("sample.stl"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**STL to PDF converter**](https://products.groupdocs.app/conversion/stl-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert STL to PDF"](conversion/net/images/convert-stl-to-pdf.png)](https://products.groupdocs.app/conversion/stl-to-pdf)