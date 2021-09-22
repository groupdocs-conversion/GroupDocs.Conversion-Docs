---
id: convert-xls-to-pdf
url: conversion/net/convert-xls-to-pdf
title: Convert XLS to PDF
description: "Converting XLS spreadsheet to PDF file is as simple as writing several lines of C# code using GroupDocs.Conversion for .NET. Check this guide for Microsoft Excel 97-2003 XLS format description and complete code to perform XLS to PDF conversion."
keywords: Convert XLS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel is known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images, and charts. Applications like Microsoft Excel lets you export workbook data to several different formats including PDF, CSV, XLSX, TXT, HTML, XPS, and several others. The XLS file format was replaced with a more open and structured format, XLSX, with the release of Microsoft Excel 2007. The latest versions still provide support for creating and reading XLS files, though XLSX is the first choice of use now.

To convert XLS to PDF file in C# just call `Convert` method like shown below:

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