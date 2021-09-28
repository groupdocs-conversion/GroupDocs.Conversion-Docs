---
id: convert-sxc-to-pdf
url: conversion/net/convert-sxc-to-pdf
title: Convert SXC to PDF
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

To convert from StarOffice Calc Spreadsheet (.sxc) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source SXC file
using (Converter converter = new Converter("sample.sxc"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to PDF converter**](https://products.groupdocs.app/conversion/sxc-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to PDF"](conversion/net/images/convert-sxc-to-pdf.png)](https://products.groupdocs.app/conversion/sxc-to-pdf)