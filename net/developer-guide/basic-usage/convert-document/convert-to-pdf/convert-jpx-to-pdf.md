---
id: convert-jpx-to-pdf
url: conversion/net/convert-jpx-to-pdf
title: Convert JPX to PDF
description: "JPX format represents JPEG 2000 Image File with .jpx extension. Learn how to convert JPX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPX is a JPEG 2000 extended file-format. JPEG 2000 is an improvement to the JPEG format.

To convert from JPEG 2000 Image File (.jpx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source JPX file
using (Converter converter = new Converter("sample.jpx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to PDF converter**](https://products.groupdocs.app/conversion/jpx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to PDF"](conversion/net/images/convert-jpx-to-pdf.png)](https://products.groupdocs.app/conversion/jpx-to-pdf)