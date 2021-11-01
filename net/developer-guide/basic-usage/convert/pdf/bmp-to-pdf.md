---
id: bmp-to-pdf
url: conversion/net/convert/bmp-to-pdf
title: Convert BMP to PDF
description: "BMP format represents Bitmap File Format with .bmp extension. Learn how to convert BMP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert BMP to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert BMP to PDF in C#
    appDescription: Convert BMP to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert BMP to PDF in C# 
        description: Quick guide about how to convert BMP to PDF in C# with high performance and accuracy.
        url: conversion/net/convert/bmp-to-pdf/#steps-to-convert-bmp-to-pdf-in-c
        steps:
        - name: Load source BMP file 
          text: Create an instance of Converter class and pass source BMP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files having extension .BMP represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images  in both monochrome as well as color format with various colour depths.

## Steps to convert BMP to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the BMP file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source BMP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source BMP file
using (var converter = new GroupDocs.Conversion.Converter("sample.bmp"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### BMP to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**BMP to PDF converter**](https://products.groupdocs.app/conversion/bmp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert BMP to PDF"](conversion/net/images/convert-to-pdf/convert-bmp-to-pdf.png)](https://products.groupdocs.app/conversion/bmp-to-pdf)