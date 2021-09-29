---
id: convert-vssm-to-doc
url: conversion/net/convert-vssm-to-doc
title: Convert VSSM to DOC
description: "VSSM format represents Microsoft Visio Macro Enabled File Format with .vssm extension. Learn how to convert VSSM to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSM to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSM extension are Microsoft Visio Stencil files that support provide support for macros. A VSSM file when opened allows running the macros to achieve the desired formatting and placement of shapes in a diagram. In general, Microsoft Visio is drawing software that allows creating files that can contain and represent user-defined information in different shapes.

## Steps to convert VSSM to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSM file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.vssm"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSM to DOC converter**](https://products.groupdocs.app/conversion/vssm-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSM to DOC"](conversion/net/images/convert-vssm-to-doc.png)](https://products.groupdocs.app/conversion/vssm-to-doc)