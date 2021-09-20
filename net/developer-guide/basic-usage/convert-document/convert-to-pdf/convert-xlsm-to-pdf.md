---
id: convert-xlsm-to-pdf
url: conversion/net/convert-xlsm-to-pdf
title: Convert XLSM to PDF
description: "XLSM files (Spreadsheet files that support Macros) can be converted to PDF format lightning fast using couple of C# code lines and powerful features of GroupDocs.Conversion for .NET. Try to convert XLSM to PDF file programmatically for free right now."
keywords: Convert XLSM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLSM extension is a type of Spreadsheet files that support Macros. From application point of view, a Macro is set of instructions that are used for automating processes. A macro is used to record the steps that are performed repeatedly and facilitates performing the actions by running the macro again. Macros are programmed with Microsoft’s Visual Basic for Applications (VBA) from within the Excel Workbook using the Visual Basic Editor and can be run/debug directly from there.

XLSM files are similar to XLM file formats but are based on the Open XML format introduced in Microsoft Office 2007. In other words, XLSM are XLSX files but with support of macros. By default, Excel itself provides several macros for common use. However, you can also record your own macros with required functions.

To convert XLSM to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source XLSM file
using (Converter converter = new Converter("sample.xlsm"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSM to PDF converter**](https://products.groupdocs.app/conversion/xlsm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSM to PDF"](conversion/net/images/convert-xlsm-to-pdf.png)](https://products.groupdocs.app/conversion/xlsm-to-pdf)