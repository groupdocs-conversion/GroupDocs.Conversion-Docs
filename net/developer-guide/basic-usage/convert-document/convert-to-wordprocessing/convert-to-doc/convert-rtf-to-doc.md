---
id: convert-rtf-to-doc
url: conversion/net/convert-rtf-to-doc
title: Convert RTF to DOC
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source RTF file
using (var converter = new GroupDocs.Conversion.Converter("sample.rtf"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to DOC converter**](https://products.groupdocs.app/conversion/rtf-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to DOC"](conversion/net/images/convert-to-doc/convert-rtf-to-doc.png)](https://products.groupdocs.app/conversion/rtf-to-doc)