---
id: convert-xlam-to-pdf
url: conversion/net/convert-xlam-to-pdf
title: Convert XLAM to PDF
description: "XLAM format represents Microsoft Excel Macro-Enabled Add-In with .xlam extension. Learn how to convert XLAM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLAM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLAM files are used to extend the modules provided by Excel. They can be added to Excel 2007 or later, or to earlier versions of Excel with Open XML component support. File used by Microsoft Excel, a program that allows users to create and edit spreadsheets; contains a macro-enabled add-in, which provides extra functionality and tools that may execute macros.

## Steps to convert XLAM to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLAM file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLAM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLAM file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlam"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLAM to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**XLAM to PDF converter**](https://products.groupdocs.app/conversion/xlam-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLAM to PDF"](conversion/net/images/convert-to-pdf/convert-xlam-to-pdf.png)](https://products.groupdocs.app/conversion/xlam-to-pdf)