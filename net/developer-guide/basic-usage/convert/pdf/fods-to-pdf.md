---
id: fods-to-pdf
url: conversion/net/convert/fods-to-pdf
title: Convert FODS to PDF
description: "FODS format represents OpenDocument Flat XML Spreadsheet with .fods extension. Learn how to convert FODS to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODS to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODS is a ZIP-compressed XML-based file format for spreadsheets, charts, presentations, and word processing documents.

## Steps to convert FODS to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODS file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODS file
using (var converter = new GroupDocs.Conversion.Converter("sample.fods"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODS to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**FODS to PDF converter**](https://products.groupdocs.app/conversion/fods-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODS to PDF"](conversion/net/images/convert-to-pdf/convert-fods-to-pdf.png)](https://products.groupdocs.app/conversion/fods-to-pdf)