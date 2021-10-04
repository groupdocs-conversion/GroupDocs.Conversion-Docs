---
id: convert-one-to-csv
url: conversion/net/convert-one-to-csv
title: Convert ONE to CSV
description: "ONE format represents Microsoft OneNote File Format with .one extension. Learn how to convert ONE to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ONE to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draftpad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips.

## Steps to convert ONE to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ONE file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ONE file
using (var converter = new GroupDocs.Conversion.Converter("sample.one"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ONE to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**ONE to CSV converter**](https://products.groupdocs.app/conversion/one-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ONE to CSV"](conversion/net/images/convert-to-csv/convert-one-to-csv.png)](https://products.groupdocs.app/conversion/one-to-csv)