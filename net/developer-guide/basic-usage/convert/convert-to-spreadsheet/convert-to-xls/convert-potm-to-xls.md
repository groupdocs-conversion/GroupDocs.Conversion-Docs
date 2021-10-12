---
id: convert-potm-to-xls
url: conversion/net/convert-potm-to-xls
title: Convert POTM to XLS
description: "POTM format represents Microsoft PowerPoint Template with .potm extension. Learn how to convert POTM to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTM to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with POTM extension are Microsoft PowerPoint template files with support for Macros. POTM files are created with PowerPoint 2007 or above and contains default settings that can be used to create further presentation files. These settings can include styles, backgrounds, colour palette, fonts and defaults along with macros that consist of custom functions for doing particular task. They may also be opened by a previous version of PowerPoint with Open XML document support installed. POTM files can be opened in Microsoft PowerPoint for editing like any other PowerPoint file.

## Steps to convert POTM to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTM file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.potm"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTM to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**POTM to XLS converter**](https://products.groupdocs.app/conversion/potm-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTM to XLS"](conversion/net/images/convert-to-xls/convert-potm-to-xls.png)](https://products.groupdocs.app/conversion/potm-to-xls)