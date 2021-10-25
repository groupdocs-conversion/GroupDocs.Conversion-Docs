---
id: vstx-to-pdf
url: conversion/net/convert/vstx-to-pdf
title: Convert VSTX to PDF
description: "VSTX format represents Microsoft Visio File Format with .vstx extension. Learn how to convert VSTX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTX to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSTX to PDF in C#
    appDescription: Convert VSTX to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSTX to PDF in C# 
        description: Quick guide about how to convert VSTX to PDF in C# with high performance and accuracy.
        url: conversion/net/convert/vstx-to-pdf/#steps-to-convert-vstx-to-pdf-in-c
        steps:
        - name: Load source VSTX file 
          text: Create an instance of Converter class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with VSTX extensions are drawing template files created with Microsoft Visio 2013 and above. These VSTX files provide a starting point for creating Visio drawings, saved as VSDX files, with default layout and settings. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VSTX to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSTX file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vstx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSTX to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTX to PDF converter**](https://products.groupdocs.app/conversion/vstx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTX to PDF"](conversion/net/images/convert-to-pdf/convert-vstx-to-pdf.png)](https://products.groupdocs.app/conversion/vstx-to-pdf)