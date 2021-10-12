---
id: vstm-to-txt
url: conversion/net/convert/vstm-to-txt
title: Convert VSTM to TXT
description: "VSTM format represents Visio Macro-Enabled Drawing Template with .vstm extension. Learn how to convert VSTM to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTM to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSTM extension are template files created with Microsoft Visio that support macros. Unlike VSDX files, files created from VSTM templates can run macros that are developed in Visual Basic for Applications (VBA) code. A template file can be created in order to provide basic settings of the document that can be utilized to generate further documents with these settings.

## Steps to convert VSTM to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSTM file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.vstm"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSTM to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTM to TXT converter**](https://products.groupdocs.app/conversion/vstm-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTM to TXT"](conversion/net/images/convert-to-txt/convert-vstm-to-txt.png)](https://products.groupdocs.app/conversion/vstm-to-txt)