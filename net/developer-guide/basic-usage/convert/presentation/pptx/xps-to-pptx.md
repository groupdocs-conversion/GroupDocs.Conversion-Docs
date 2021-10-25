---
id: xps-to-pptx
url: conversion/net/convert/xps-to-pptx
title: Convert XPS to PPTX
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert XPS to PPTX in C#
    appDescription: Convert XPS to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert XPS to PPTX in C# 
        description: Quick guide about how to convert XPS to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/xps-to-pptx/#steps-to-convert-xps-to-pptx-in-c
        steps:
        - name: Load source XPS file 
          text: Create an instance of Converter class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPTX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xps"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to PPTX converter**](https://products.groupdocs.app/conversion/xps-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to PPTX"](conversion/net/images/convert-to-pptx/convert-xps-to-pptx.png)](https://products.groupdocs.app/conversion/xps-to-pptx)