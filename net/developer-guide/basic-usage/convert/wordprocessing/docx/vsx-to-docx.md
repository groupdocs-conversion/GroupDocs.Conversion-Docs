---
id: vsx-to-docx
url: conversion/net/convert/vsx-to-docx
title: Convert VSX to DOCX
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VSX to DOCX in C#
    appDescription: Convert VSX to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VSX to DOCX in C# 
        description: Some description
        url: conversion/net/convert/vsx-to-docx/#steps-to-convert-vsx-to-docx-in-c
        steps:
        - name: Load source VSX file 
          text: Create an instance of Converter class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

## Steps to convert VSX to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSX file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsx"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSX to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to DOCX converter**](https://products.groupdocs.app/conversion/vsx-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to DOCX"](conversion/net/images/convert-to-docx/convert-vsx-to-docx.png)](https://products.groupdocs.app/conversion/vsx-to-docx)