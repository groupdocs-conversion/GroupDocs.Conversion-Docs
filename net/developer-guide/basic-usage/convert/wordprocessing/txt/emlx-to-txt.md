---
id: emlx-to-txt
url: conversion/net/convert/emlx-to-txt
title: Convert EMLX to TXT
description: "EMLX format represents Apple Mail Message with .emlx extension. Learn how to convert EMLX to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMLX to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The EMLX file format is implemented and developed by Apple. The Apple Mail application uses the EMLX file format for exporting the emails. There are other applications as well such as GroupDocs.Conversion App that can open the EMLX files and convert these to other file formats.

## Steps to convert EMLX to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMLX file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMLX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMLX file
using (var converter = new GroupDocs.Conversion.Converter("sample.emlx"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMLX to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**EMLX to TXT converter**](https://products.groupdocs.app/conversion/emlx-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMLX to TXT"](conversion/net/images/convert-to-txt/convert-emlx-to-txt.png)](https://products.groupdocs.app/conversion/emlx-to-txt)