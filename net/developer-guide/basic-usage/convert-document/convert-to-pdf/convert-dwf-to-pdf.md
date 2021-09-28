---
id: convert-dwf-to-pdf
url: conversion/net/convert-dwf-to-pdf
title: Convert DWF to PDF
description: "DWF format represents Design Web Format with .dwf extension. Learn how to convert DWF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing, or printing design files. It contains graphics and text as part of design data and reduces the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn't require the recipient to know about the usage of CAD software that created the original drawing.

To convert from Design Web Format (.dwf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

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