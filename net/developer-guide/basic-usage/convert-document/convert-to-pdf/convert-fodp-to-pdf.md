---
id: convert-fodp-to-pdf
url: conversion/net/convert-fodp-to-pdf
title: Convert FODP to PDF
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to PDF converter**](https://products.groupdocs.app/conversion/fodp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to PDF"](conversion/net/images/convert-fodp-to-pdf.png)](https://products.groupdocs.app/conversion/fodp-to-pdf)