---
id: convert-vsdx-to-pdf
url: conversion/net/convert-vsdx-to-pdf
title: Convert VSDX to PDF
description: "VSDX format represents Microsoft Visio File Format with .vsdx extension. Learn how to convert VSDX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

## Steps to convert VSDX to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDX file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsdx"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDX to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to PDF converter**](https://products.groupdocs.app/conversion/vsdx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to PDF"](conversion/net/images/convert-vsdx-to-pdf.png)](https://products.groupdocs.app/conversion/vsdx-to-pdf)