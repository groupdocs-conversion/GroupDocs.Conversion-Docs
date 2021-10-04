---
id: convert-odt-to-csv
url: conversion/net/convert-odt-to-csv
title: Convert ODT to CSV
description: "ODT format represents Open Document Text with .odt extension. Learn how to convert ODT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODT to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google's web-based word processor included with Google Drive can open the ODT files for editing.

## Steps to convert ODT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODT file
using (var converter = new GroupDocs.Conversion.Converter("sample.odt"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**ODT to CSV converter**](https://products.groupdocs.app/conversion/odt-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODT to CSV"](conversion/net/images/convert-to-csv/convert-odt-to-csv.png)](https://products.groupdocs.app/conversion/odt-to-csv)