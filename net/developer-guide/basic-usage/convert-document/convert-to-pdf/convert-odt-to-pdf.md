---
id: convert-odt-to-pdf
url: conversion/net/convert-odt-to-pdf
title: Convert ODT to PDF
description: "ODT format represents Open Document Text with .odt extension. Learn how to convert ODT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google's web-based word processor included with Google Drive can open the ODT files for editing.

To convert from Open Document Text (.odt) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source ODT file
using (Converter converter = new Converter("sample.odt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**ODT to PDF converter**](https://products.groupdocs.app/conversion/odt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODT to PDF"](conversion/net/images/convert-odt-to-pdf.png)](https://products.groupdocs.app/conversion/odt-to-pdf)