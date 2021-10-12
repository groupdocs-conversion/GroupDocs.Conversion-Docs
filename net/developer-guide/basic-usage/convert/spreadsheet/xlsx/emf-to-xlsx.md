---
id: emf-to-xlsx
url: conversion/net/convert/emf-to-xlsx
title: Convert EMF to XLSX
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

## Steps to convert EMF to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMF file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMF file
using (var converter = new GroupDocs.Conversion.Converter("sample.emf"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMF to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to XLSX converter**](https://products.groupdocs.app/conversion/emf-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to XLSX"](conversion/net/images/convert-to-xlsx/convert-emf-to-xlsx.png)](https://products.groupdocs.app/conversion/emf-to-xlsx)