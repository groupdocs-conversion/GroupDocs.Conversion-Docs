---
id: convert-vsd-to-pdf
url: conversion/net/convert-vsd-to-pdf
title: Convert VSD to PDF
description: "VSD format represents Visio Drawing File Format with .vsd extension. Learn how to convert VSD to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSD to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSD files are drawings created with Microsoft Visio application to represent variety of graphical objects and the interconnection between these. Such drawings can contain visual objects such as visual objects, flow charts, UML diagram, information flow, organizational charts, software diagrams, network layout, database models, objects mapping and other similar information. Microsoft Visio offers the capability to convert Visio files to a number of different file formats including PNG, BMP, PDF and others.

## Steps to convert VSD to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSD file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSD file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsd"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSD to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**VSD to PDF converter**](https://products.groupdocs.app/conversion/vsd-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSD to PDF"](conversion/net/images/convert-to-pdf/convert-vsd-to-pdf.png)](https://products.groupdocs.app/conversion/vsd-to-pdf)