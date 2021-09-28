---
id: convert-rtf-to-pdf
url: conversion/net/convert-rtf-to-pdf
title: Convert RTF to PDF
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

To convert from Rich Text File Format (.rtf) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source RTF file
using (Converter converter = new Converter("sample.rtf"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to PDF converter**](https://products.groupdocs.app/conversion/rtf-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to PDF"](conversion/net/images/convert-rtf-to-pdf.png)](https://products.groupdocs.app/conversion/rtf-to-pdf)