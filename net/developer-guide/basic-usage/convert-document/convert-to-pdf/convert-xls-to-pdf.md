---
id: convert-xls-to-pdf
url: conversion/net/convert-xls-to-pdf
title: Convert XLS to PDF
description: "XLS format represents Microsoft Excel Binary File Format with .xls extension. Learn how to convert XLS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

To convert from Microsoft Excel Binary File Format (.xls) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source XLS file
using (Converter converter = new Converter("sample.xls"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XLS to PDF converter**](https://products.groupdocs.app/conversion/xls-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLS to PDF"](conversion/net/images/convert-xls-to-pdf.png)](https://products.groupdocs.app/conversion/xls-to-pdf)