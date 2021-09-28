---
id: convert-mhtml-to-pdf
url: conversion/net/convert-mhtml-to-pdf
title: Convert MHTML to PDF
description: "MHTML format represents MIME Encapsulation of Aggregate HTML with .mhtml extension. Learn how to convert MHTML to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHTML to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

To convert from MIME Encapsulation of Aggregate HTML (.mhtml) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

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