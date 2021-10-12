---
id: dotm-to-docx
url: conversion/net/convert/dotm-to-docx
title: Convert DOTM to DOCX
description: "DOTM format represents Microsoft Word Macro-Enabled Template with .dotm extension. Learn how to convert DOTM to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTM to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with DOTM extension represents template file created with Microsoft Word 2007 or higher. It is similar to the popular DOCX file format other than it retains the user defined settings for reuse in case of creating new documents. Such documents are more often used in offices where a standard template file is generated with settings like page information, margins, default layout and macros, and is used to create new documents from it when required. DOTM files, however, save macros, that are a series of commands in the form of recorded actions for automatic completion of a task. This helps save time in carrying out actions that are repeated in completion of a task.

## Steps to convert DOTM to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTM file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.dotm"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOTM to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTM to DOCX converter**](https://products.groupdocs.app/conversion/dotm-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTM to DOCX"](conversion/net/images/convert-to-docx/convert-dotm-to-docx.png)](https://products.groupdocs.app/conversion/dotm-to-docx)