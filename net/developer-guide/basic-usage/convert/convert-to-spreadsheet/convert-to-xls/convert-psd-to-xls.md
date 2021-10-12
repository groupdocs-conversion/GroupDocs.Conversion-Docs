---
id: convert-psd-to-xls
url: conversion/net/convert-psd-to-xls
title: Convert PSD to XLS
description: "PSD format represents Adobe Photoshop Document with .psd extension. Learn how to convert PSD to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PSD to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PSD, Photoshop Document, represents Adobe Photoshop's native file format used for graphics designing and development. PSD files may include image layers, adjustment layers, layer masks, annotations, file information, keywords, and other Photoshop-specific elements. Photoshop files have default extension as PSD and have a maximum height and width of 30,000 pixels, and a length limit of two gigabytes.

## Steps to convert PSD to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PSD file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PSD file
using (var converter = new GroupDocs.Conversion.Converter("sample.psd"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PSD to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**PSD to XLS converter**](https://products.groupdocs.app/conversion/psd-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PSD to XLS"](conversion/net/images/convert-to-xls/convert-psd-to-xls.png)](https://products.groupdocs.app/conversion/psd-to-xls)