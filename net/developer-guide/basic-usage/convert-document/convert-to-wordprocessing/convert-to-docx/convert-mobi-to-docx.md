---
id: convert-mobi-to-docx
url: conversion/net/convert-mobi-to-docx
title: Convert MOBI to DOCX
description: "MOBI format represents Mobipocket eBook with .mobi extension. Learn how to convert MOBI to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MOBI to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The MOBI file format is one of the most widely used ebook file formats. The format is an enhancement to the old OEB (Open Ebook Format) format and was used as the proprietary format for Mobipocket Reader. Like EPUB, it is supported by almost all modern e-readers specifically by mobile devices with low bandwidth. The format can be converted to several other formats such as PDF, EPUB, and several other formats using publicly available software applications such as the Kindle app.

## Steps to convert MOBI to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MOBI file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MOBI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MOBI file
using (var converter = new GroupDocs.Conversion.Converter("sample.mobi"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MOBI to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**MOBI to DOCX converter**](https://products.groupdocs.app/conversion/mobi-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MOBI to DOCX"](conversion/net/images/convert-to-docx/convert-mobi-to-docx.png)](https://products.groupdocs.app/conversion/mobi-to-docx)