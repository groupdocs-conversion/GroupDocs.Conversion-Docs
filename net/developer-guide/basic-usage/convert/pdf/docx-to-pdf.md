---
id: docx-to-pdf
url: conversion/net/convert/docx-to-pdf
title: Convert DOCX to PDF
description: "DOCX format represents Microsoft Word Open XML Document with .docx extension. Learn how to convert DOCX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCX to PDF in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DOCX to PDF in C#
    appDescription: Convert DOCX to PDF natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DOCX to PDF in C# 
        description: Some description
        url: conversion/net/convert/docx-to-pdf/#steps-to-convert-docx-to-pdf-in-c
        steps:
        - name: Load source DOCX file 
          text: Create an instance of Converter class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

## Steps to convert DOCX to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCX file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOCX to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCX to PDF converter**](https://products.groupdocs.app/conversion/docx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCX to PDF"](conversion/net/images/convert-to-pdf/convert-docx-to-pdf.png)](https://products.groupdocs.app/conversion/docx-to-pdf)