---
id: convert-jpm-to-docx
url: conversion/net/convert-jpm-to-docx
title: Convert JPM to DOCX
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to DOCX converter**](https://products.groupdocs.app/conversion/jpm-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to DOCX"](conversion/net/images/convert-to-docx/convert-jpm-to-docx.png)](https://products.groupdocs.app/conversion/jpm-to-docx)