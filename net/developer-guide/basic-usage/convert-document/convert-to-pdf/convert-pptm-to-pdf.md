---
id: convert-pptm-to-pdf
url: conversion/net/convert-pptm-to-pdf
title: Convert PPTM to PDF
description: "Follow this article to learn how to convert PPTM Macro-enabled Presentation files created with Microsoft PowerPoint 2007 or later into PDF format using GroupDocs.Conversion for .NET and C# language."
keywords: Convert PPTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can’t execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

To convert PPTM to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source PPTM file
using (Converter converter = new Converter("sample.pptm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to PDF converter**](https://products.groupdocs.app/conversion/pptm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to PDF"](conversion/net/images/convert-pptm-to-pdf.png)](https://products.groupdocs.app/conversion/pptm-to-pdf)