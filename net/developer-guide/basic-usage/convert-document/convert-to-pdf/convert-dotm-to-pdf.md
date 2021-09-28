---
id: convert-dotm-to-pdf
url: conversion/net/convert-dotm-to-pdf
title: Convert DOTM to PDF
description: "DOTM format represents Microsoft Word Macro-Enabled Template with .dotm extension. Learn how to convert DOTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with DOTM extension represents template file created with Microsoft Word 2007 or higher. It is similar to the popular DOCX file format other than it retains the user defined settings for reuse in case of creating new documents. Such documents are more often used in offices where a standard template file is generated with settings like page information, margins, default layout and macros, and is used to create new documents from it when required. DOTM files, however, save macros, that are a series of commands in the form of recorded actions for automatic completion of a task. This helps save time in carrying out actions that are repeated in completion of a task.

To convert from Microsoft Word Macro-Enabled Template (.dotm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source DOTM file
using (Converter converter = new Converter("sample.dotm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTM to PDF converter**](https://products.groupdocs.app/conversion/dotm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTM to PDF"](conversion/net/images/convert-dotm-to-pdf.png)](https://products.groupdocs.app/conversion/dotm-to-pdf)