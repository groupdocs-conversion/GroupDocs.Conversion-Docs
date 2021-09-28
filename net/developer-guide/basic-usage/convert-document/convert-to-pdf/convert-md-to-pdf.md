---
id: convert-md-to-pdf
url: conversion/net/convert-md-to-pdf
title: Convert MD to PDF
description: "MD format represents Markdown with .md extension. Learn how to convert MD to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

To convert from Markdown (.md) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MD file
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

GroupDocs.Conversion for .NET provides an online [**MD to PDF converter**](https://products.groupdocs.app/conversion/md-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to PDF"](conversion/net/images/convert-md-to-pdf.png)](https://products.groupdocs.app/conversion/md-to-pdf)