---
id: convert-wmf-to-pdf
url: conversion/net/convert-wmf-to-pdf
title: Convert WMF to PDF
description: "WMF format represents Windows Metafile with .wmf extension. Learn how to convert WMF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WMF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with WMF extension represent Microsoft Windows Metafile (WMF) for storing vector as well as bitmap-format images data. To be more accurate, WMF belongs to the vector file format category of Graphics file formats that is device independent. Windows Graphical Device Interface (GDI) uses the functions stored in a WMF file to display an image on the screen.

To convert from Windows Metafile (.wmf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source WMF file
using (Converter converter = new Converter("sample.wmf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**WMF to PDF converter**](https://products.groupdocs.app/conversion/wmf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WMF to PDF"](conversion/net/images/convert-wmf-to-pdf.png)](https://products.groupdocs.app/conversion/wmf-to-pdf)