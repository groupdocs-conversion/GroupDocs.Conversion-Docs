---
id: convert-dwfx-to-pdf
url: conversion/net/convert-dwfx-to-pdf
title: Convert DWFX to PDF
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

To convert from Design Web Format XPS (.dwfx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DWFX file
using (Converter converter = new Converter("sample.dwfx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to PDF converter**](https://products.groupdocs.app/conversion/dwfx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to PDF"](conversion/net/images/convert-dwfx-to-pdf.png)](https://products.groupdocs.app/conversion/dwfx-to-pdf)