---
id: convert-cdr-to-xls
url: conversion/net/convert-cdr-to-xls
title: Convert CDR to XLS
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

## Steps to convert CDR to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CDR file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CDR file
using (var converter = new GroupDocs.Conversion.Converter("sample.cdr"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CDR to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to XLS converter**](https://products.groupdocs.app/conversion/cdr-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to XLS"](conversion/net/images/convert-to-xls/convert-cdr-to-xls.png)](https://products.groupdocs.app/conversion/cdr-to-xls)