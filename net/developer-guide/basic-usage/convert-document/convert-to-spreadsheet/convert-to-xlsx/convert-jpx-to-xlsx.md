---
id: convert-jpx-to-xlsx
url: conversion/net/convert-jpx-to-xlsx
title: Convert JPX to XLSX
description: "JPX format represents JPEG 2000 Image File with .jpx extension. Learn how to convert JPX to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPX to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPX is a JPEG 2000 extended file-format. JPEG 2000 is an improvement to the JPEG format.

## Steps to convert JPX to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPX file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpx"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPX to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to XLSX converter**](https://products.groupdocs.app/conversion/jpx-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to XLSX"](conversion/net/images/convert-to-xlsx/convert-jpx-to-xlsx.png)](https://products.groupdocs.app/conversion/jpx-to-xlsx)