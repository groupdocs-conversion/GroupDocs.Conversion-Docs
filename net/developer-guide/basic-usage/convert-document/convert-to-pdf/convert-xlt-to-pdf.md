---
id: convert-xlt-to-pdf
url: conversion/net/convert-xlt-to-pdf
title: Convert XLT to PDF
description: "XLT format represents Microsoft Excel Template with .xlt extension. Learn how to convert XLT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

To convert from Microsoft Excel Template (.xlt) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source XLT file
using (Converter converter = new Converter("sample.xlt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XLT to PDF converter**](https://products.groupdocs.app/conversion/xlt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLT to PDF"](conversion/net/images/convert-xlt-to-pdf.png)](https://products.groupdocs.app/conversion/xlt-to-pdf)