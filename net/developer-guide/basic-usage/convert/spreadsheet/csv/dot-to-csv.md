---
id: dot-to-csv
url: conversion/net/convert/dot-to-csv
title: Convert DOT to CSV
description: "DOT format represents Microsoft Word Document Template with .dot extension. Learn how to convert DOT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOT to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DOT extension are template files created by Microsoft Word to have pre-formatted settings for generation of further DOC or DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from these. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dot"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**DOT to CSV converter**](https://products.groupdocs.app/conversion/dot-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOT to CSV"](conversion/net/images/convert-to-csv/convert-dot-to-csv.png)](https://products.groupdocs.app/conversion/dot-to-csv)