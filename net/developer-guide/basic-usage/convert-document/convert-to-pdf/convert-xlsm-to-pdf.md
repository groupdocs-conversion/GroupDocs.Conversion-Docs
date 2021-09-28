---
id: convert-xlsm-to-pdf
url: conversion/net/convert-xlsm-to-pdf
title: Convert XLSM to PDF
description: "XLSM format represents Microsoft Excel Macro-Enabled Spreadsheet with .xlsm extension. Learn how to convert XLSM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLSM extension is a type of Spreasheet files that support Macros. From application point of view, a Macro is set of instructions that are used for automating processes. A macro is used to record the steps that are performed repeatedly and facilitates performing the actions by running the macro again. Macros are programmed with Microsoft's Visual Basic for Applications (VBA) from within the Excel Workbook using the Visual Basic Editor and can be run/debug directly from there.

To convert from Microsoft Excel Macro-Enabled Spreadsheet (.xlsm) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

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