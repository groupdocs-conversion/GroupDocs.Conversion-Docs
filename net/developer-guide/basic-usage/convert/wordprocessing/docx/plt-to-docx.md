---
id: plt-to-docx
url: conversion/net/convert/plt-to-docx
title: Convert PLT to DOCX
description: "PLT format represents PLT (HPGL) with .plt extension. Learn how to convert PLT to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PLT to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An HPGL(Hewlett-Packard Graphics Language) file contains an instruction set for plotter control, developed by Hewlett-Packard. Hewlett-Packard plotters use this file to draw and print vector and raster content on the paper.

## Steps to convert PLT to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PLT file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.plt"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PLT to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**PLT to DOCX converter**](https://products.groupdocs.app/conversion/plt-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PLT to DOCX"](conversion/net/images/convert-to-docx/convert-plt-to-docx.png)](https://products.groupdocs.app/conversion/plt-to-docx)