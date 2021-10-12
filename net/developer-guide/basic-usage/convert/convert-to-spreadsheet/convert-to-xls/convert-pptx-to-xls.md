---
id: convert-pptx-to-xls
url: conversion/net/convert-pptx-to-xls
title: Convert PPTX to XLS
description: "PPTX format represents PowerPoint Open XML Presentation with .pptx extension. Learn how to convert PPTX to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTX to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media.

## Steps to convert PPTX to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTX file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPTX to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTX to XLS converter**](https://products.groupdocs.app/conversion/pptx-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTX to XLS"](conversion/net/images/convert-to-xls/convert-pptx-to-xls.png)](https://products.groupdocs.app/conversion/pptx-to-xls)