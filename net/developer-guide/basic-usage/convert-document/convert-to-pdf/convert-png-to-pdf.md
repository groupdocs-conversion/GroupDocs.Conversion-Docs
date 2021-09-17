---
id: convert-png-to-pdf
url: conversion/net/convert-png-to-pdf
title: Convert PNG to PDF
description: "Learn how to seamlessly convert a PNG image into PDF file with a couple of simple steps. Use GroupDocs.Conversion for .NET to transform images into PDF and many other file types."
keywords: Convert PNG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PNG, Portable Network Graphics, refers to a type of raster image file format that use loseless compression. This file format was created as a replacement of Graphics Interchange Format (GIF) and has no copyright limitations. However, PNG file format does not support animations. PNG file format supports loseless image compression that makes it popular among its users. With the passage of time, PNG has evolved as one of the mostly used image file format.

To convert PNG to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source PNG file
using (Converter converter = new Converter("sample.png"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PNG to PDF converter**](https://products.groupdocs.app/conversion/png-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PNG to PDF"](conversion/net/images/convert-png-to-pdf.png)](https://products.groupdocs.app/conversion/png-to-pdf)