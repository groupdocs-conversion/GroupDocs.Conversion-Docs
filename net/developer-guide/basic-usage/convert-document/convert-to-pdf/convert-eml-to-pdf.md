---
id: convert-eml-to-pdf
url: conversion/net/convert-eml-to-pdf
title: Convert EML to PDF
description: "EML format represents E-Mail Message File with .eml extension. Learn how to convert EML to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EML to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EML file format represents email messages saved using Outlook and other relevant applications. Almost all emailing clients support this file format for its compliance with RFC-822 Internet Message Format Standard. Microsoft Outlook is default software for opening EML message types. EML files can be used for saving to disc as well as sending out to recipients using communication protocols.

To convert from E-Mail Message File (.eml) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source EML file
using (Converter converter = new Converter("sample.eml"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EML to PDF converter**](https://products.groupdocs.app/conversion/eml-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EML to PDF"](conversion/net/images/convert-eml-to-pdf.png)](https://products.groupdocs.app/conversion/eml-to-pdf)