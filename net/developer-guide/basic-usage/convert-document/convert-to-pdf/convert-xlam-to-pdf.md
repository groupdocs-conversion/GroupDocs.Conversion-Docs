---
id: convert-xlam-to-pdf
url: conversion/net/convert-xlam-to-pdf
title: Convert XLAM to PDF
description: "XLAM format represents Microsoft Excel Macro-Enabled Add-In with .xlam extension. Learn how to convert XLAM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLAM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLAM files are used to extend the modules provided by Excel. They can be added to Excel 2007 or later, or to earlier versions of Excel with Open XML component support. File used by Microsoft Excel, a program that allows users to create and edit spreadsheets; contains a macro-enabled add-in, which provides extra functionality and tools that may execute macros.

To convert from Microsoft Excel Macro-Enabled Add-In (.xlam) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source XLAM file
using (Converter converter = new Converter("sample.xlam"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XLAM to PDF converter**](https://products.groupdocs.app/conversion/xlam-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLAM to PDF"](conversion/net/images/convert-xlam-to-pdf.png)](https://products.groupdocs.app/conversion/xlam-to-pdf)