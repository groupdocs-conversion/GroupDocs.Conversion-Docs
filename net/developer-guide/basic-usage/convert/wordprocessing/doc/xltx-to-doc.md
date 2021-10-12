---
id: xltx-to-doc
url: conversion/net/convert/xltx-to-doc
title: Convert XLTX to DOC
description: "XLTX format represents Microsoft Excel Open XML Template with .xltx extension. Learn how to convert XLTX to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLTX to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLTX extension represent Microsoft Excel Template files that are based on the Office OpenXML file format specifications. It is used to create a standard template file that can be utilized to generate XLSX files that exhibit the same settings as specified in the XLTX file.

## Steps to convert XLTX to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLTX file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xltx"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLTX to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**XLTX to DOC converter**](https://products.groupdocs.app/conversion/xltx-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLTX to DOC"](conversion/net/images/convert-to-doc/convert-xltx-to-doc.png)](https://products.groupdocs.app/conversion/xltx-to-doc)