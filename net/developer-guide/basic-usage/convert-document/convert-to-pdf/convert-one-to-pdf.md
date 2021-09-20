---
id: convert-one-to-pdf
url: conversion/net/convert-one-to-pdf
title: Convert ONE to PDF
description: "Converting Microsoft OneNote files to PDF is so easy and straightforward with Groupdocs.Conversion for .NET. Just a few lines of C# code to convert ONE note file to PDF document, check our guide to learn how."
keywords: Convert ONE to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File represented by .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draft pad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips. Microsoft now offers online version of OneNote as part of Office365 where Notes can be shared with other OneNote users over the internet.

To convert ONE to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source ONE file
using (Converter converter = new Converter("sample.one"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**ONE to PDF converter**](https://products.groupdocs.app/conversion/one-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ONE to PDF"](conversion/net/images/convert-one-to-pdf.png)](https://products.groupdocs.app/conversion/one-to-pdf)