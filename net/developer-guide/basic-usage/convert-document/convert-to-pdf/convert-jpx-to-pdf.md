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

## Steps to convert JPX to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPX file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpx"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPX to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to PDF converter**](https://products.groupdocs.app/conversion/jpx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to PDF"](conversion/net/images/convert-jpx-to-pdf.png)](https://products.groupdocs.app/conversion/jpx-to-pdf)