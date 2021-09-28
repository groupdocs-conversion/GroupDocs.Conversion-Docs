---
id: convert-dxf-to-pdf
url: conversion/net/convert-dxf-to-pdf
title: Convert DXF to PDF
description: "DXF format represents Autodesk Drawing Exchange File Format with .dxf extension. Learn how to convert DXF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DXF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DXF, Drawing Interchange Format, or Drawing Exchange Format, is a tagged data representation of AutoCAD drawing file. Each element in the file has a prefix integer number called a group code. This group code actually represents the element that follows and indicates the meaning of a data element for a given object type. DXF makes it possible to represent almost all user-specified information in a drawing file.

To convert from Autodesk Drawing Exchange File Format (.dxf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DXF file
using (Converter converter = new Converter("sample.dxf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DXF to PDF converter**](https://products.groupdocs.app/conversion/dxf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DXF to PDF"](conversion/net/images/convert-dxf-to-pdf.png)](https://products.groupdocs.app/conversion/dxf-to-pdf)