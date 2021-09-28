---
id: convert-cf2-to-pdf
url: conversion/net/convert-cf2-to-pdf
title: Convert CF2 to PDF
description: "CF2 format represents Common File Format File with .cf2 extension. Learn how to convert CF2 to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CF2 to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .cf2 extension is a CAD file format that contains 3D package designs or other model data for die-cutting. Most of the CAD/CAM machines can process and cut these files. It was created by the National Space Science Data Center (NSSDC) to provide self-describing data storage and manipulation format that matches the structure of scientific data and applications such as statistical and numerical methods, visualization, and management. 

To convert from Common File Format File (.cf2) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source CF2 file
using (Converter converter = new Converter("sample.cf2"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**CF2 to PDF converter**](https://products.groupdocs.app/conversion/cf2-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CF2 to PDF"](conversion/net/images/convert-cf2-to-pdf.png)](https://products.groupdocs.app/conversion/cf2-to-pdf)