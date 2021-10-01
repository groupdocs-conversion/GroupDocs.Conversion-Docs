---
id: convert-dot-to-txt
url: conversion/net/convert-dot-to-txt
title: Convert DOT to TXT
description: "DOT format represents Microsoft Word Document Template with .dot extension. Learn how to convert DOT to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOT to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DOT extension are template files created by Microsoft Word to have pre-formatted settings for generation of further DOC or DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from these. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOT to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOT file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dot"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOT to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DOT to TXT converter**](https://products.groupdocs.app/conversion/dot-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOT to TXT"](conversion/net/images/convert-to-txt/convert-dot-to-txt.png)](https://products.groupdocs.app/conversion/dot-to-txt)