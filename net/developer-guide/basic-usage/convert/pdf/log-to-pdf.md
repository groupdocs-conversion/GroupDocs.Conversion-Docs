---
id: log-to-pdf
url: conversion/net/convert/log-to-pdf
title: Convert LOG to PDF
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert LOG to PDF in C#
    appDescription: Convert LOG to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert LOG to PDF in C# 
        description: Quick guide about how to convert LOG to PDF in C# with high performance and accuracy.
        url: conversion/net/convert/log-to-pdf/#steps-to-convert-log-to-pdf-in-c
        steps:
        - name: Load source LOG file 
          text: Create an instance of Converter class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to PDF converter**](https://products.groupdocs.app/conversion/log-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to PDF"](conversion/net/images/convert-to-pdf/convert-log-to-pdf.png)](https://products.groupdocs.app/conversion/log-to-pdf)