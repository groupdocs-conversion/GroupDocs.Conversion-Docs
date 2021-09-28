---
id: convert-html-to-pdf
url: conversion/net/convert-html-to-pdf
title: Convert HTML to PDF
description: "HTML format represents Hyper Text Markup Language with .html extension. Learn how to convert HTML to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTML to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as language of the web, HTML has evolved with requirements of new information requirements to be displayed as part of web pages. The latest variant is known as HTML 5 that gives a lot of flexibility for working with the language. HTML pages are either received from server, where these are hosted, or can be loaded from local system as well.

To convert from Hyper Text Markup Language (.html) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source HTML file
using (Converter converter = new Converter("sample.html"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**HTML to PDF converter**](https://products.groupdocs.app/conversion/html-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTML to PDF"](conversion/net/images/convert-html-to-pdf.png)](https://products.groupdocs.app/conversion/html-to-pdf)