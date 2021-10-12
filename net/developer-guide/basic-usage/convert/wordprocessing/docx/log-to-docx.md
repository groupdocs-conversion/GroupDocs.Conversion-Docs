---
id: log-to-docx
url: conversion/net/convert/log-to-docx
title: Convert LOG to DOCX
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to DOCX converter**](https://products.groupdocs.app/conversion/log-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to DOCX"](conversion/net/images/convert-to-docx/convert-log-to-docx.png)](https://products.groupdocs.app/conversion/log-to-docx)