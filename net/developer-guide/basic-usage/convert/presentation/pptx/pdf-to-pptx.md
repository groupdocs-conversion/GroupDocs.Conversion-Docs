---
id: pdf-to-pptx
url: conversion/net/convert/pdf-to-pptx
title: Convert PDF to PPTX
description: "PDF format represents Portable Document with .pdf extension. Learn how to convert PDF to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PDF to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

## Steps to convert PDF to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PDF file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PDF to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**PDF to PPTX converter**](https://products.groupdocs.app/conversion/pdf-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PDF to PPTX"](conversion/net/images/convert-to-pptx/convert-pdf-to-pptx.png)](https://products.groupdocs.app/conversion/pdf-to-pptx)