---
id: convert-cmx-to-pdf
url: conversion/net/convert-cmx-to-pdf
title: Convert CMX to PDF
description: "CMX format represents Corel Metafile Exchange Image File with .cmx extension. Learn how to convert CMX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CMX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with CMX extension are Corel Exchange image file format (also known as Corel Metafile Exchange) that is used as presentation by CorelSuite applications. It contains image data as vector graphics as well as metadata that describes the image. CMX files can be opened by CorelDraw, Corel Presentations, Paint Shop Pro and some versions of Adobe Illustrator. CMX files can be converted to other formats such as JPG and EPS.

To convert from Corel Metafile Exchange Image File (.cmx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source CMX file
using (Converter converter = new Converter("sample.cmx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**CMX to PDF converter**](https://products.groupdocs.app/conversion/cmx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CMX to PDF"](conversion/net/images/convert-cmx-to-pdf.png)](https://products.groupdocs.app/conversion/cmx-to-pdf)