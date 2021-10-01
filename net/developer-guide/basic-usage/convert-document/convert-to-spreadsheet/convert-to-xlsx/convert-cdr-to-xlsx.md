---
id: convert-cdr-to-xlsx
url: conversion/net/convert-cdr-to-xlsx
title: Convert CDR to XLSX
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

## Steps to convert CDR to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CDR file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CDR file
using (var converter = new GroupDocs.Conversion.Converter("sample.cdr"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CDR to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to XLSX converter**](https://products.groupdocs.app/conversion/cdr-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to XLSX"](conversion/net/images/convert-to-xlsx/convert-cdr-to-xlsx.png)](https://products.groupdocs.app/conversion/cdr-to-xlsx)