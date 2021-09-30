---
id: convert-potm-to-docx
url: conversion/net/convert-potm-to-docx
title: Convert POTM to DOCX
description: "POTM format represents Microsoft PowerPoint Template with .potm extension. Learn how to convert POTM to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTM to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with POTM extension are Microsoft PowerPoint template files with support for Macros. POTM files are created with PowerPoint 2007 or above and contains default settings that can be used to create further presentation files. These settings can include styles, backgrounds, colour palette, fonts and defaults along with macros that consist of custom functions for doing particular task. They may also be opened by a previous version of PowerPoint with Open XML document support installed. POTM files can be opened in Microsoft PowerPoint for editing like any other PowerPoint file.

## Steps to convert POTM to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTM file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.potm"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTM to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**POTM to DOCX converter**](https://products.groupdocs.app/conversion/potm-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTM to DOCX"](conversion/net/images/convert-to-docx/convert-potm-to-docx.png)](https://products.groupdocs.app/conversion/potm-to-docx)