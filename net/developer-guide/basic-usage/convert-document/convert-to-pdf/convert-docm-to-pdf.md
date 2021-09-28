---
id: convert-docm-to-pdf
url: conversion/net/convert-docm-to-pdf
title: Convert DOCM to PDF
description: "DOCM format represents Microsoft Word Macro-Enabled Document with .docm extension. Learn how to convert DOCM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DOCM files are Microsoft Word 2007 or higher generated documents with the ability to run macros. It is similar to DOCX file format but the ability to run macros makes it different from DOCX. Like DOCX, DOCM files can be store text, images, tables, shapes, charts and other contents. The capability to run macros make it easy to save time by executing the series of commands in the form of recorded actions for automatic completion of a task. DOCM files can be opened and edited in Microsoft Word 2007 and above.

To convert from Microsoft Word Macro-Enabled Document (.docm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DOCM file
using (Converter converter = new Converter("sample.docm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCM to PDF converter**](https://products.groupdocs.app/conversion/docm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCM to PDF"](conversion/net/images/convert-docm-to-pdf.png)](https://products.groupdocs.app/conversion/docm-to-pdf)