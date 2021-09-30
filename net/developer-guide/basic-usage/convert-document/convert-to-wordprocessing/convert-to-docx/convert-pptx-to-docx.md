---
id: convert-pptx-to-docx
url: conversion/net/convert-pptx-to-docx
title: Convert PPTX to DOCX
description: "PPTX format represents PowerPoint Open XML Presentation with .pptx extension. Learn how to convert PPTX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTX to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media.

## Steps to convert PPTX to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTX file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPTX to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTX to DOCX converter**](https://products.groupdocs.app/conversion/pptx-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTX to DOCX"](conversion/net/images/convert-to-docx/convert-pptx-to-docx.png)](https://products.groupdocs.app/conversion/pptx-to-docx)