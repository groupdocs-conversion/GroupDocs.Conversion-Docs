---
id: convert-jpg-to-pdf
url: conversion/net/convert-jpg-to-pdf
title: Convert JPG to PDF
description: "This article demonstrates how to convert JPG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

To convert JPG to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source JPG file
using (Converter converter = new Converter("sample.jpg"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPG to PDF converter**](https://products.groupdocs.app/conversion/jpg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPG to PDF"](conversion/net/images/convert-jpg-to-pdf.png)](https://products.groupdocs.app/conversion/jpg-to-pdf)