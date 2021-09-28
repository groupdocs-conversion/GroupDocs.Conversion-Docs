---
id: convert-ots-to-pdf
url: conversion/net/convert-ots-to-pdf
title: Convert OTS to PDF
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

To convert from OpenDocument Spreadsheet Template (.ots) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source OTS file
using (Converter converter = new Converter("sample.ots"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to PDF converter**](https://products.groupdocs.app/conversion/ots-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to PDF"](conversion/net/images/convert-ots-to-pdf.png)](https://products.groupdocs.app/conversion/ots-to-pdf)