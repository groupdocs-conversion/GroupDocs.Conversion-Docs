---
id: jpeg-to-pdf
url: conversion/net/convert/jpeg-to-pdf
title: Convert JPEG to PDF
description: "JPEG format represents JPEG Image with .jpeg extension. Learn how to convert JPEG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPEG to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert JPEG to PDF in C#
    appDescription: Convert JPEG to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert JPEG to PDF in C# 
        description: Some description
        url: conversion/net/convert/jpeg-to-pdf/#steps-to-convert-jpeg-to-pdf-in-c
        steps:
        - name: Load source JPEG file 
          text: Create an instance of Converter class and pass source JPEG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality. JPEG image file format was standardized by the Joint Photographic Experts Group and, hence, the name JPEG. The format has been the choice of storing and transmitting photographic images on the web. Almost all Operating systems now have viewers that support visualization of JPEG images, which are often stored with JPG extension as well. Even the web browsers support visualization of JPEG images.

## Steps to convert JPEG to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPEG file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPEG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPEG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpeg"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPEG to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**JPEG to PDF converter**](https://products.groupdocs.app/conversion/jpeg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPEG to PDF"](conversion/net/images/convert-to-pdf/convert-jpeg-to-pdf.png)](https://products.groupdocs.app/conversion/jpeg-to-pdf)