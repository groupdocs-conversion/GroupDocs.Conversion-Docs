---
id: convert-mhtml-to-pdf
url: conversion/net/convert-mhtml-to-pdf
title: Convert MHTML to PDF
description: "Convert web-pages in MHT or MHTML format to PDF format using C# programming language and GroupDocs.Conversion for .NET."
keywords: Convert MHTML to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. It stores the HTML of the webpage, as well as linked resources in the webpage, which may include CSS, JavaScript, images, and audio files. MHTML files are primarily used by web developers to save the current state of a webpage for archival purposes.
MHTML files can be opened in a variety of applications such as browsers and Microsoft Word.

To convert MHTML to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source MHTML file
using (Converter converter = new Converter("sample.mhtml"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MHTML to PDF converter**](https://products.groupdocs.app/conversion/mhtml-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHTML to PDF"](conversion/net/images/convert-mhtml-to-pdf.png)](https://products.groupdocs.app/conversion/mhtml-to-pdf)