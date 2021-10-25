---
id: dotx-to-pptx
url: conversion/net/convert/dotx-to-pptx
title: Convert DOTX to PPTX
description: "DOTX format represents Word Open XML Document Template with .dotx extension. Learn how to convert DOTX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTX to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DOTX to PPTX in C#
    appDescription: Convert DOTX to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DOTX to PPTX in C# 
        description: Quick guide about how to convert DOTX to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/dotx-to-pptx/#steps-to-convert-dotx-to-pptx-in-c
        steps:
        - name: Load source DOTX file 
          text: Create an instance of Converter class and pass source DOTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with DOTX extension are template files created by Microsoft Word to have pre-formatted settings for a generation of further DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from this template. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOTX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dotx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOTX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTX to PPTX converter**](https://products.groupdocs.app/conversion/dotx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTX to PPTX"](conversion/net/images/convert-to-pptx/convert-dotx-to-pptx.png)](https://products.groupdocs.app/conversion/dotx-to-pptx)