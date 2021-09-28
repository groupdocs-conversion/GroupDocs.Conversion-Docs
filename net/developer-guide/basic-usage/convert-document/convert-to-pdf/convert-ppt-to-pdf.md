---
id: convert-ppt-to-pdf
url: conversion/net/convert-ppt-to-pdf
title: Convert PPT to PDF
description: "PPT format represents PowerPoint Presentation with .ppt extension. Learn how to convert PPT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with PPT extension represents PowerPoint file that consists of a collection of slides for displaying as SlideShow. It specifies the Binary File Format used by Microsoft PowerPoint 97-2003. A PPT file can contain several different types of information such as text, bulleted points, images, multimedia and other embedded OLE objects. Microsoft came up with newer file format for PowerPoint, known as PPTX, from 2007 onwards that is based on Office OpenXML and is different from this binary file format.

To convert from PowerPoint Presentation (.ppt) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PPT file
using (Converter converter = new Converter("sample.ppt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPT to PDF converter**](https://products.groupdocs.app/conversion/ppt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPT to PDF"](conversion/net/images/convert-ppt-to-pdf.png)](https://products.groupdocs.app/conversion/ppt-to-pdf)