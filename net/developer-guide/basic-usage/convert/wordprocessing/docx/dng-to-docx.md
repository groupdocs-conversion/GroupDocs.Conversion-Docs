---
id: dng-to-docx
url: conversion/net/convert/dng-to-docx
title: Convert DNG to DOCX
description: "DNG format represents Digital Camera Image Format with .dng extension. Learn how to convert DNG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DNG to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DNG to DOCX in C#
    appDescription: Convert DNG to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DNG to DOCX in C# 
        description: Some description
        url: conversion/net/convert/dng-to-docx/#steps-to-convert-dng-to-docx-in-c
        steps:
        - name: Load source DNG file 
          text: Create an instance of Converter class and pass source DNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

DNG is a digital camera image format used for the storage of raw files. It has been developed by Adobe in September 2004. It was basically developed for digital photography. DNG is an extension of TIFF/EP standard format and uses metadata significantly. In order to manipulate raw data from digital cameras with ease of flexibility and artistic control, photographers opt camera raw files.

## Steps to convert DNG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DNG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dng"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DNG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DNG to DOCX converter**](https://products.groupdocs.app/conversion/dng-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DNG to DOCX"](conversion/net/images/convert-to-docx/convert-dng-to-docx.png)](https://products.groupdocs.app/conversion/dng-to-docx)