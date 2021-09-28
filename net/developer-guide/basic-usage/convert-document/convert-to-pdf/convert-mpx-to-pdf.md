---
id: convert-mpx-to-pdf
url: conversion/net/convert-mpx-to-pdf
title: Convert MPX to PDF
description: "MPX format represents Microsoft Project Exchange File with .mpx extension. Learn how to convert MPX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MPX, Microsoft Exchange File Format, is an ASCII file format for transferring project information between Microsoft Project (MSP) and other applications that support the MPX file format such as Primavera Project Planner, Sciforma, and Timberline Precision Estimating. The MPX file format allows you to transfer project information that cannot appear in a table, such as detailed resource assignment information, calendar information, or information in the Project Info dialog box.

To convert from Microsoft Project Exchange File (.mpx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MPX file
using (Converter converter = new Converter("sample.mpx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MPX to PDF converter**](https://products.groupdocs.app/conversion/mpx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPX to PDF"](conversion/net/images/convert-mpx-to-pdf.png)](https://products.groupdocs.app/conversion/mpx-to-pdf)