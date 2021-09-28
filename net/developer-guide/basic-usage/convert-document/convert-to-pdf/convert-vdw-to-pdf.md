---
id: convert-vdw-to-pdf
url: conversion/net/convert-vdw-to-pdf
title: Convert VDW to PDF
description: "VDW format represents Visio Web Drawing with .vdw extension. Learn how to convert VDW to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDW to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VDW is the Visio Graphics Service file format that specifies the streams and storages required for rendering a Web drawing. A web drawing is a collection of drawing pages, shapes, fonts, images, data connections, and diagram update information that can be rendered as a vector or raster drawing. VDW files can be opened in Microsoft Visio as well but are primarily saved for use on the web.

To convert from Visio Web Drawing (.vdw) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VDW file
using (Converter converter = new Converter("sample.vdw"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VDW to PDF converter**](https://products.groupdocs.app/conversion/vdw-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDW to PDF"](conversion/net/images/convert-vdw-to-pdf.png)](https://products.groupdocs.app/conversion/vdw-to-pdf)