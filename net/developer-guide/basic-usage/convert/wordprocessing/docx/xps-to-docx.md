---
id: xps-to-docx
url: conversion/net/convert/xps-to-docx
title: Convert XPS to DOCX
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert XPS to DOCX in C#
    appDescription: Convert XPS to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert XPS to DOCX in C# 
        description: Quick guide about how to convert XPS to DOCX in C# with high performance and accuracy.
        url: conversion/net/convert/xps-to-docx/#steps-to-convert-xps-to-docx-in-c
        steps:
        - name: Load source XPS file 
          text: Create an instance of Converter class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xps"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to DOCX converter**](https://products.groupdocs.app/conversion/xps-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to DOCX"](conversion/net/images/convert-to-docx/convert-xps-to-docx.png)](https://products.groupdocs.app/conversion/xps-to-docx)