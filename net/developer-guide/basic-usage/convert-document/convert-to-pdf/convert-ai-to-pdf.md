---
id: convert-ai-to-pdf
url: conversion/net/convert-ai-to-pdf
title: Convert AI to PDF
description: "AI format represents Adobe Illustrator with .ai extension. Learn how to convert AI to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert AI to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with an .ai extension is an Adobe Illustrator Artwork file that contains vector graphics on a single page. It uses points to create paths for displaying the image data, thus making it safe from losing image quality if it is enlarged. AI format finds its major usage for logos and print media. AI files can be opened with Adobe Illustrator, Adobe Acrobat DC, PaintShop Pro, and CorelDraw Graphics tools.

To convert from Adobe Illustrator (.ai) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source AI file
using (Converter converter = new Converter("sample.ai"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**AI to PDF converter**](https://products.groupdocs.app/conversion/ai-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert AI to PDF"](conversion/net/images/convert-ai-to-pdf.png)](https://products.groupdocs.app/conversion/ai-to-pdf)