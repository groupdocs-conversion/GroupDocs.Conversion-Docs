---
id: convert-jpeg-to-pdf
url: conversion/net/convert-jpeg-to-pdf
title: Convert JPEG to PDF
description: "JPEG format represents JPEG Image with .jpeg extension. Learn how to convert JPEG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPEG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality. JPEG image file format was standardized by the Joint Photographic Experts Group and, hence, the name JPEG. The format has been the choice of storing and transmitting photographic images on the web. Almost all Operating systems now have viewers that support visualization of JPEG images, which are often stored with JPG extension as well. Even the web browsers support visualization of JPEG images.

To convert from JPEG Image (.jpeg) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JPEG file
using (Converter converter = new Converter("sample.jpeg"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPEG to PDF converter**](https://products.groupdocs.app/conversion/jpeg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPEG to PDF"](conversion/net/images/convert-jpeg-to-pdf.png)](https://products.groupdocs.app/conversion/jpeg-to-pdf)