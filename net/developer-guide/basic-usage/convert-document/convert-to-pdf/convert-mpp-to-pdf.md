---
id: convert-mpp-to-pdf
url: conversion/net/convert-mpp-to-pdf
title: Convert MPP to PDF
description: "Learn how to convert Microsoft Project data file to PDF format using a few lines of C# code. Groupdocs.Conversion for .NET provides an ability to convert MPP to PDF quickly and with attention to details."
keywords: Convert MPP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with a .mpp extension is a Microsoft Project data file that stores information related to project management in an integrated manner. Microsoft has developed this proprietary file format to make it compatible with Microsoft Project (MSP), their project management software product. Other than MPP, MSP can work with project XML schema. Many applications and APIs allow MPPs to be converted to other file formats. Microsoft now has an online Project Server where project management files can be uploaded for collaboration by multiple users.

To convert MPP to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source MPP file
using (Converter converter = new Converter("sample.mpp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MPP to PDF converter**](https://products.groupdocs.app/conversion/mpp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPP to PDF"](conversion/net/images/convert-mpp-to-pdf.png)](https://products.groupdocs.app/conversion/mpp-to-pdf)