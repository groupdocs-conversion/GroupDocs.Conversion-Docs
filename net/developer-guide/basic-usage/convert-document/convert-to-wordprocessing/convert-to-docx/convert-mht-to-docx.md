---
id: convert-mht-to-docx
url: conversion/net/convert-mht-to-docx
title: Convert MHT to DOCX
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mht"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHT to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to DOCX converter**](https://products.groupdocs.app/conversion/mht-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to DOCX"](conversion/net/images/convert-to-docx/convert-mht-to-docx.png)](https://products.groupdocs.app/conversion/mht-to-docx)