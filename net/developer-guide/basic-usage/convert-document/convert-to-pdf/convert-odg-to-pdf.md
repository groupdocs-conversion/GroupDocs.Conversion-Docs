---
id: convert-odg-to-pdf
url: conversion/net/convert-odg-to-pdf
title: Convert ODG to PDF
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

To convert from OpenDocument Drawing File (.odg) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source ODG file
using (Converter converter = new Converter("sample.odg"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to PDF converter**](https://products.groupdocs.app/conversion/odg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to PDF"](conversion/net/images/convert-odg-to-pdf.png)](https://products.groupdocs.app/conversion/odg-to-pdf)