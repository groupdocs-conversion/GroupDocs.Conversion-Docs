---
id: convert-markdown-to-pdf
url: conversion/net/convert-markdown-to-pdf
title: Convert MARKDOWN to PDF
description: "Check this article to learn how GroupDocs.Conversion for .NET library allows to convert MD file into PDF document. Just a few simple steps to transform markdown files into PDF format in C#."
keywords: Convert MARKDOWN to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .md or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

To convert MARKDOWN to PDF file just call `Convert` method like shown below:

```csharp
// Load the source MARKDOWN file
using (Converter converter = new Converter("sample.md"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MARKDOWN to PDF converter**](https://products.groupdocs.app/conversion/markdown-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MARKDOWN to PDF"](conversion/net/images/convert-markdown-to-pdf.png)](https://products.groupdocs.app/conversion/markdown-to-pdf)