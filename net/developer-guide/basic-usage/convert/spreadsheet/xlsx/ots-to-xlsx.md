---
id: ots-to-xlsx
url: conversion/net/convert/ots-to-xlsx
title: Convert OTS to XLSX
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

## Steps to convert OTS to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTS file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ots"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTS to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to XLSX converter**](https://products.groupdocs.app/conversion/ots-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to XLSX"](conversion/net/images/convert-to-xlsx/convert-ots-to-xlsx.png)](https://products.groupdocs.app/conversion/ots-to-xlsx)