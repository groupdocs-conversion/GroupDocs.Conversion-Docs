---
id: convert-potm-to-pdf
url: conversion/net/convert-potm-to-pdf
title: Convert POTM to PDF
description: "POTM format represents Microsoft PowerPoint Template with .potm extension. Learn how to convert POTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with POTM extension are Microsoft PowerPoint template files with support for Macros. POTM files are created with PowerPoint 2007 or above and contains default settings that can be used to create further presentation files. These settings can include styles, backgrounds, colour palette, fonts and defaults along with macros that consist of custom functions for doing particular task. They may also be opened by a previous version of PowerPoint with Open XML document support installed. POTM files can be opened in Microsoft PowerPoint for editing like any other PowerPoint file.

To convert from Microsoft PowerPoint Template (.potm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source POTM file
using (Converter converter = new Converter("sample.potm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**POTM to PDF converter**](https://products.groupdocs.app/conversion/potm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTM to PDF"](conversion/net/images/convert-potm-to-pdf.png)](https://products.groupdocs.app/conversion/potm-to-pdf)