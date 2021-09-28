---
id: convert-dgn-to-pdf
url: conversion/net/convert-dgn-to-pdf
title: Convert DGN to PDF
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

To convert from MicroStation Design File (.dgn) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DGN file
using (Converter converter = new Converter("sample.dgn"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to PDF converter**](https://products.groupdocs.app/conversion/dgn-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to PDF"](conversion/net/images/convert-dgn-to-pdf.png)](https://products.groupdocs.app/conversion/dgn-to-pdf)