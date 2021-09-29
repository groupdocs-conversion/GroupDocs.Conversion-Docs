---
id: convert-dicom-to-pdf
url: conversion/net/convert-dicom-to-pdf
title: Convert DICOM to PDF
description: "DICOM format represents Digital Imaging and Communications in Medicine with .dicom extension. Learn how to convert DICOM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DICOM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DICOM is the acronym for Digital Imaging and Communications in Medicine and pertains to the field of Medical Informatics. DICOM is the combination of file format definition and a network communications protocol. DICOM uses the .DCM extension. .DCM exists in two different formats i.e. format 1.x and format 2.x. DCM Format 1.x is further available in two versions normal and extended.

## Steps to convert DICOM to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DICOM file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DICOM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DICOM file
using (var converter = new GroupDocs.Conversion.Converter("sample.dicom"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DICOM to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**DICOM to PDF converter**](https://products.groupdocs.app/conversion/dcm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DICOM to PDF"](conversion/net/images/convert-dicom-to-pdf.png)](https://products.groupdocs.app/conversion/dcm-to-pdf)