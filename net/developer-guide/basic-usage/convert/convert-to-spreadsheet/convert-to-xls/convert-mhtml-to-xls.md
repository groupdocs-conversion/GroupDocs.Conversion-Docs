---
id: convert-mhtml-to-xls
url: conversion/net/convert-mhtml-to-xls
title: Convert MHTML to XLS
description: "MHTML format represents MIME Encapsulation of Aggregate HTML with .mhtml extension. Learn how to convert MHTML to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHTML to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

## Steps to convert MHTML to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHTML file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHTML file
using (var converter = new GroupDocs.Conversion.Converter("sample.mhtml"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHTML to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**MHTML to XLS converter**](https://products.groupdocs.app/conversion/mhtml-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHTML to XLS"](conversion/net/images/convert-to-xls/convert-mhtml-to-xls.png)](https://products.groupdocs.app/conversion/mhtml-to-xls)