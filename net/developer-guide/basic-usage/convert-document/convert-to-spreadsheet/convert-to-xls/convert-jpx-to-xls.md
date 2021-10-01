---
id: convert-jpx-to-xls
url: conversion/net/convert-jpx-to-xls
title: Convert JPX to XLS
description: "JPX format represents JPEG 2000 Image File with .jpx extension. Learn how to convert JPX to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPX to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPX is a JPEG 2000 extended file-format. JPEG 2000 is an improvement to the JPEG format.

## Steps to convert JPX to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPX file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpx"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPX to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to XLS converter**](https://products.groupdocs.app/conversion/jpx-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to XLS"](conversion/net/images/convert-to-xls/convert-jpx-to-xls.png)](https://products.groupdocs.app/conversion/jpx-to-xls)