---
id: convert-j2c-to-pdf
url: conversion/net/convert-j2c-to-pdf
title: Convert J2C to PDF
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2c"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2C to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to PDF converter**](https://products.groupdocs.app/conversion/j2c-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to PDF"](conversion/net/images/convert-j2c-to-pdf.png)](https://products.groupdocs.app/conversion/j2c-to-pdf)