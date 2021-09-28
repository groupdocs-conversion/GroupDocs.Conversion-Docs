---
id: convert-docx-to-pdf
url: conversion/net/convert-docx-to-pdf
title: Convert DOCX to PDF
description: "DOCX format represents Microsoft Word Open XML Document with .docx extension. Learn how to convert DOCX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

To convert from Microsoft Word Open XML Document (.docx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DOCX file
using (Converter converter = new Converter("sample.docx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCX to PDF converter**](https://products.groupdocs.app/conversion/docx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCX to PDF"](conversion/net/images/convert-docx-to-pdf.png)](https://products.groupdocs.app/conversion/docx-to-pdf)