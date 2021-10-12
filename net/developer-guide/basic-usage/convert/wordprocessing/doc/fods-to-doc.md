---
id: fods-to-doc
url: conversion/net/convert/fods-to-doc
title: Convert FODS to DOC
description: "FODS format represents OpenDocument Flat XML Spreadsheet with .fods extension. Learn how to convert FODS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODS to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODS is a ZIP-compressed XML-based file format for spreadsheets, charts, presentations, and word processing documents.

## Steps to convert FODS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODS file
using (var converter = new GroupDocs.Conversion.Converter("sample.fods"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**FODS to DOC converter**](https://products.groupdocs.app/conversion/fods-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODS to DOC"](conversion/net/images/convert-to-doc/convert-fods-to-doc.png)](https://products.groupdocs.app/conversion/fods-to-doc)