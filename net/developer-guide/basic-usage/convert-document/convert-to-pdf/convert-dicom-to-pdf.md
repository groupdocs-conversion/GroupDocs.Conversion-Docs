---
id: convert-dicom-to-pdf
url: conversion/net/convert-dicom-to-pdf
title: Convert DICOM to PDF
description: "Groupdocs.Conversion for .NET library provides an easy and intuitive way to convert medical images in DICOM format to PDF files. Check this article to perform DCM to PDF conversion in C#."
keywords: Convert DICOM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DICOM is the acronym for Digital Imaging and Communications in Medicine and pertains to the field of Medical Informatics. DICOM is used for the integration of medical imaging devices like printers, servers, scanners etc from various vendors and also contains identification data of each patient for uniqueness. DICOM files can be shared between two parties if they are capable of receiving image data in DICOM format. The communication part of DICOM is application layer protocol and uses TCP/IP to communicate between entities. Versions supported by web services are 1.0, 1.1, 2 or later.

To convert DICOM to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source DICOM file
using (Converter converter = new Converter("sample.dcm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DICOM to PDF converter**](https://products.groupdocs.app/conversion/dicom-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DICOM to PDF"](conversion/net/images/convert-dcm-to-pdf.png)](https://products.groupdocs.app/conversion/dicom-to-pdf)