---
id: convert-log-to-pdf
url: conversion/net/convert-log-to-pdf
title: Convert LOG to PDF
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

To convert from Log File (.log) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source LOG file
using (Converter converter = new Converter("sample.log"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to PDF converter**](https://products.groupdocs.app/conversion/log-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to PDF"](conversion/net/images/convert-log-to-pdf.png)](https://products.groupdocs.app/conversion/log-to-pdf)