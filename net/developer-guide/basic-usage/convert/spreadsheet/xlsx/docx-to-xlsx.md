---
id: docx-to-xlsx
url: conversion/net/convert/docx-to-xlsx
title: Convert DOCX to XLSX
description: "DOCX format represents Microsoft Word Open XML Document with .docx extension. Learn how to convert DOCX to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCX to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

## Steps to convert DOCX to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCX file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOCX to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCX to XLSX converter**](https://products.groupdocs.app/conversion/docx-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCX to XLSX"](conversion/net/images/convert-to-xlsx/convert-docx-to-xlsx.png)](https://products.groupdocs.app/conversion/docx-to-xlsx)