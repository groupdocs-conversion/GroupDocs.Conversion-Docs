---
id: convert-dwf-to-pdf
url: conversion/net/convert-dwf-to-pdf
title: Convert DWF to PDF
description: "The following guide demonstrates how to convert DWF drawing files to PDF format for easy viewing, sharing and printing. You can convert DWF and other CAD formats to PDF in C# with help of Groupdocs.Conversion for .NET."
keywords: Convert DWF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing or printing design files. It contains graphics and text as part of design data and reduce the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn’t require the recipient to know about the usage of CAD software that created the original drawing. The contents of DWF file format can be simple and include just a single sheet or complex enough to have fonts, color, and images.

To convert DWF to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source DWF file
using (Converter converter = new Converter("sample.dwf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DWF to PDF converter**](https://products.groupdocs.app/conversion/dwf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWF to PDF"](conversion/net/images/convert-dwf-to-pdf.png)](https://products.groupdocs.app/conversion/dwf-to-pdf)