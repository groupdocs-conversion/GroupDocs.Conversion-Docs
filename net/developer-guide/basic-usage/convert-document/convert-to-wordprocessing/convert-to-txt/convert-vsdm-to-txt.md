---
id: convert-vsdm-to-txt
url: conversion/net/convert-vsdm-to-txt
title: Convert VSDM to TXT
description: "VSDM format represents Visio Macro-Enabled Drawing with .vsdm extension. Learn how to convert VSDM to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDM to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSDM extension are drawing files created with Microsoft Visio application that supports macros. VSDM files are OPC/XML drawings that are similar to VSDX but also provide the capability to run macros when the file is opened. Macros are user-defined actions/steps that are developed in Visual Basic for Applications (VBA) and can be used to perform repetitive tasks.

## Steps to convert VSDM to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDM file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDM file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsdm"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDM to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDM to TXT converter**](https://products.groupdocs.app/conversion/vsdm-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDM to TXT"](conversion/net/images/convert-to-txt/convert-vsdm-to-txt.png)](https://products.groupdocs.app/conversion/vsdm-to-txt)