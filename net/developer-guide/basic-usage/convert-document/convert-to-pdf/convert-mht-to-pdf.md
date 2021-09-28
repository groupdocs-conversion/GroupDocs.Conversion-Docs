---
id: convert-mht-to-pdf
url: conversion/net/convert-mht-to-pdf
title: Convert MHT to PDF
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

To convert from MIME Encapsulation of Aggregate HTML (.mht) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MHT file
using (Converter converter = new Converter("sample.mht"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to PDF converter**](https://products.groupdocs.app/conversion/mht-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to PDF"](conversion/net/images/convert-mht-to-pdf.png)](https://products.groupdocs.app/conversion/mht-to-pdf)