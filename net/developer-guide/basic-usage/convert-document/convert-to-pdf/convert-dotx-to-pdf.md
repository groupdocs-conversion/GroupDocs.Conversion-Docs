---
id: convert-dotx-to-pdf
url: conversion/net/convert-dotx-to-pdf
title: Convert DOTX to PDF
description: "DOTX format represents Word Open XML Document Template with .dotx extension. Learn how to convert DOTX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DOTX extension are template files created by Microsoft Word to have pre-formatted settings for a generation of further DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from this template. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

To convert from Word Open XML Document Template (.dotx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DOTX file
using (Converter converter = new Converter("sample.dotx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTX to PDF converter**](https://products.groupdocs.app/conversion/dotx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTX to PDF"](conversion/net/images/convert-dotx-to-pdf.png)](https://products.groupdocs.app/conversion/dotx-to-pdf)