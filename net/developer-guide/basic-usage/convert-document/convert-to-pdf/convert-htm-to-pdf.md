---
id: convert-htm-to-pdf
url: conversion/net/convert-htm-to-pdf
title: Convert HTM to PDF
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

To convert from Hypertext Markup Language File (.htm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source HTM file
using (Converter converter = new Converter("sample.htm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PDF converter**](https://products.groupdocs.app/conversion/htm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PDF"](conversion/net/images/convert-htm-to-pdf.png)](https://products.groupdocs.app/conversion/htm-to-pdf)