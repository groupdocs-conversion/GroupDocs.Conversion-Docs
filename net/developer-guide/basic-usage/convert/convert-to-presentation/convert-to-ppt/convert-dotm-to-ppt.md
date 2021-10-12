---
id: convert-dotm-to-ppt
url: conversion/net/convert-dotm-to-ppt
title: Convert DOTM to PPT
description: "DOTM format represents Microsoft Word Macro-Enabled Template with .dotm extension. Learn how to convert DOTM to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTM to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with DOTM extension represents template file created with Microsoft Word 2007 or higher. It is similar to the popular DOCX file format other than it retains the user defined settings for reuse in case of creating new documents. Such documents are more often used in offices where a standard template file is generated with settings like page information, margins, default layout and macros, and is used to create new documents from it when required. DOTM files, however, save macros, that are a series of commands in the form of recorded actions for automatic completion of a task. This helps save time in carrying out actions that are repeated in completion of a task.

## Steps to convert DOTM to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTM file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.dotm"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOTM to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTM to PPT converter**](https://products.groupdocs.app/conversion/dotm-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTM to PPT"](conversion/net/images/convert-to-ppt/convert-dotm-to-ppt.png)](https://products.groupdocs.app/conversion/dotm-to-ppt)