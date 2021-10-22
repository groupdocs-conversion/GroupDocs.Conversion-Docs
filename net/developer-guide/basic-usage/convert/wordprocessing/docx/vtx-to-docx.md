---
id: vtx-to-docx
url: conversion/net/convert/vtx-to-docx
title: Convert VTX to DOCX
description: "VTX format represents Microsoft Visio Drawing Template with .vtx extension. Learn how to convert VTX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VTX to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VTX to DOCX in C#
    appDescription: Convert VTX to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VTX to DOCX in C# 
        description: Some description
        url: conversion/net/convert/vtx-to-docx/#steps-to-convert-vtx-to-docx-in-c
        steps:
        - name: Load source VTX file 
          text: Create an instance of Converter class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

## Steps to convert VTX to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VTX file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vtx"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VTX to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**VTX to DOCX converter**](https://products.groupdocs.app/conversion/vtx-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VTX to DOCX"](conversion/net/images/convert-to-docx/convert-vtx-to-docx.png)](https://products.groupdocs.app/conversion/vtx-to-docx)