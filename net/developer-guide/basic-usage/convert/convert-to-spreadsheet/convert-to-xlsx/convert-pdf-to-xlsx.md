---
id: convert-pdf-to-xlsx
url: conversion/net/convert-pdf-to-xlsx
title: Convert PDF to XLSX
description: "PDF format represents Portable Document with .pdf extension. Learn how to convert PDF to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PDF to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

## Steps to convert PDF to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PDF file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PDF to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**PDF to XLSX converter**](https://products.groupdocs.app/conversion/pdf-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PDF to XLSX"](conversion/net/images/convert-to-xlsx/convert-pdf-to-xlsx.png)](https://products.groupdocs.app/conversion/pdf-to-xlsx)