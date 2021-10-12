---
id: djvu-to-docx
url: conversion/net/convert/djvu-to-docx
title: Convert DJVU to DOCX
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to DOCX converter**](https://products.groupdocs.app/conversion/djvu-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to DOCX"](conversion/net/images/convert-to-docx/convert-djvu-to-docx.png)](https://products.groupdocs.app/conversion/djvu-to-docx)