---
id: convert-mhtml-to-doc
url: conversion/net/convert-mhtml-to-doc
title: Convert MHTML to DOC
description: "MHTML format represents MIME Encapsulation of Aggregate HTML with .mhtml extension. Learn how to convert MHTML to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHTML to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

## Steps to convert MHTML to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHTML file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHTML file
using (var converter = new GroupDocs.Conversion.Converter("sample.mhtml"))
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

GroupDocs.Conversion for .NET provides an online [**MHTML to DOC converter**](https://products.groupdocs.app/conversion/mhtml-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHTML to DOC"](conversion/net/images/convert-mhtml-to-doc.png)](https://products.groupdocs.app/conversion/mhtml-to-doc)