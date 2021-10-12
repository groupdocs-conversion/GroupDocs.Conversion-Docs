---
id: dotx-to-txt
url: conversion/net/convert/dotx-to-txt
title: Convert DOTX to TXT
description: "DOTX format represents Word Open XML Document Template with .dotx extension. Learn how to convert DOTX to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTX to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DOTX extension are template files created by Microsoft Word to have pre-formatted settings for a generation of further DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from this template. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOTX to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTX file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dotx"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOTX to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTX to TXT converter**](https://products.groupdocs.app/conversion/dotx-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTX to TXT"](conversion/net/images/convert-to-txt/convert-dotx-to-txt.png)](https://products.groupdocs.app/conversion/dotx-to-txt)