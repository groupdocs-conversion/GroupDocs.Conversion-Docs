---
id: odp-to-pdf
url: conversion/net/convert/odp-to-pdf
title: Convert ODP to PDF
description: "ODP format represents OpenDocument Presentation File Format with .odp extension. Learn how to convert ODP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

## Steps to convert ODP to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODP file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.odp"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODP to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**ODP to PDF converter**](https://products.groupdocs.app/conversion/odp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODP to PDF"](conversion/net/images/convert-to-pdf/convert-odp-to-pdf.png)](https://products.groupdocs.app/conversion/odp-to-pdf)