---
id: convert-mpt-to-csv
url: conversion/net/convert-mpt-to-csv
title: Convert MPT to CSV
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpt"))
{
    // Set the convert options for CSV format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPT to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to CSV converter**](https://products.groupdocs.app/conversion/mpt-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to CSV"](conversion/net/images/convert-to-csv/convert-mpt-to-csv.png)](https://products.groupdocs.app/conversion/mpt-to-csv)