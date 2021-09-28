---
id: convert-emf-to-pdf
url: conversion/net/convert-emf-to-pdf
title: Convert EMF to PDF
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

To convert from Enhanced Metafile Format (.emf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source EMF file
using (Converter converter = new Converter("sample.emf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to PDF converter**](https://products.groupdocs.app/conversion/emf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to PDF"](conversion/net/images/convert-emf-to-pdf.png)](https://products.groupdocs.app/conversion/emf-to-pdf)