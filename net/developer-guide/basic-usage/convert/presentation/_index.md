---
id: convert-to-presentation
url: conversion/net/convert/presentation
title: Convert Presentation
weight: 4
description: "This article demonstrates how to convert documents to PowerPoint presentation of PPT, PPTX, ODP and may other formats with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert to Presentation, Convert to PPT, Convert to PPTX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## About Presentation File Formats

You must be familiar with **PPTX** and **PPT** extension files, these are Presentation file formats that store collection of records to accommodate presentation data such as: slides, shapes, text, animations, video, audio and embedded objects. A presentation can be saved/converted into other file formats as well such as PDF, BMP, PNG, JPEG, and XPS.

Common Presentation file extensions and their associated file formats include **PPTX**, **PPT** and **ODP**.

## Convert PDF to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PDF file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

## Convert PPT to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPT file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppt"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```
