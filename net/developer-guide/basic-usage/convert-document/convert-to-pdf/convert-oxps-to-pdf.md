---
id: convert-oxps-to-pdf
url: conversion/net/convert-oxps-to-pdf
title: Convert OXPS to PDF
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

## Steps to convert OXPS to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OXPS file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OXPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OXPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.oxps"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OXPS to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to PDF converter**](https://products.groupdocs.app/conversion/oxps-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to PDF"](conversion/net/images/convert-oxps-to-pdf.png)](https://products.groupdocs.app/conversion/oxps-to-pdf)