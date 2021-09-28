---
id: convert-ppsm-to-pdf
url: conversion/net/convert-ppsm-to-pdf
title: Convert PPSM to PDF
description: "PPSM format represents Microsoft PowerPoint Slide Show with .ppsm extension. Learn how to convert PPSM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is PPTM which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as slide show, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening it in PowerPoint.

To convert from Microsoft PowerPoint Slide Show (.ppsm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source PPSM file
using (Converter converter = new Converter("sample.ppsm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSM to PDF converter**](https://products.groupdocs.app/conversion/ppsm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSM to PDF"](conversion/net/images/convert-ppsm-to-pdf.png)](https://products.groupdocs.app/conversion/ppsm-to-pdf)