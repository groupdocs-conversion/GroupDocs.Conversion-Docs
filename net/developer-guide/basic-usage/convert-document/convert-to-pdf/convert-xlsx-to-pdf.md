---
id: convert-xlsx-to-pdf
url: conversion/net/convert-xlsx-to-pdf
title: Convert XLSX to PDF
description: "XLSX format represents Microsoft Excel Open XML Spreadsheet with .xlsx extension. Learn how to convert XLSX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

To convert from Microsoft Excel Open XML Spreadsheet (.xlsx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source XLSX file
using (Converter converter = new Converter("sample.xlsx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSX to PDF converter**](https://products.groupdocs.app/conversion/xlsx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSX to PDF"](conversion/net/images/convert-xlsx-to-pdf.png)](https://products.groupdocs.app/conversion/xlsx-to-pdf)