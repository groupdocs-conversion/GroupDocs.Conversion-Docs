---
id: convert-tsv-to-pdf
url: conversion/net/convert-tsv-to-pdf
title: Convert TSV to PDF
description: "This documentation article explains how to convert Tab-Separated Values (TSV) file to PDF format using a few lines of C# code. Use GroupDocs.Conversion for .NET to transform text/tab-separated-values files into PDF documents."
keywords: Convert TSV to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. Each record in a TSV file is contained in a single line of text file where each field value is separated by a tab character. Media type for TSV file format is text/tab-separated-values.

To convert TSV to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source TSV file
using (Converter converter = new Converter("sample.tsv"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to PDF converter**](https://products.groupdocs.app/conversion/tsv-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to PDF"](conversion/net/images/convert-tsv-to-pdf.png)](https://products.groupdocs.app/conversion/tsv-to-pdf)