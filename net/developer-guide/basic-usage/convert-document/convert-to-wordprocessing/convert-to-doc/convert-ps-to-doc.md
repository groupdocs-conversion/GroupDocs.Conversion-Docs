---
id: convert-ps-to-doc
url: conversion/net/convert-ps-to-doc
title: Convert PS to DOC
description: "PS format represents PostScript (PS) with .ps extension. Learn how to convert PS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PS to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straightforward interpretation.

## Steps to convert PS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source PS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ps"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**PS to DOC converter**](https://products.groupdocs.app/conversion/ps-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PS to DOC"](conversion/net/images/convert-to-doc/convert-ps-to-doc.png)](https://products.groupdocs.app/conversion/ps-to-doc)