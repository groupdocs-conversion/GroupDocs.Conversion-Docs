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

To convert from OpenDocument Flat XML Presentation (.fodp) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source FODP file
using (Converter converter = new Converter("sample.fodp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to PDF converter**](https://products.groupdocs.app/conversion/fodp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to PDF"](conversion/net/images/convert-fodp-to-pdf.png)](https://products.groupdocs.app/conversion/fodp-to-pdf)