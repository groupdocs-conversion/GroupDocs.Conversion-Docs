---
id: convert-odt-to-xlsx
url: conversion/net/convert-odt-to-xlsx
title: Convert ODT to XLSX
description: "ODT format represents Open Document Text with .odt extension. Learn how to convert ODT to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODT to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google's web-based word processor included with Google Drive can open the ODT files for editing.

## Steps to convert ODT to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODT file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODT file
using (var converter = new GroupDocs.Conversion.Converter("sample.odt"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODT to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**ODT to XLSX converter**](https://products.groupdocs.app/conversion/odt-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODT to XLSX"](conversion/net/images/convert-to-xlsx/convert-odt-to-xlsx.png)](https://products.groupdocs.app/conversion/odt-to-xlsx)