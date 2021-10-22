---
id: cmx-to-docx
url: conversion/net/convert/cmx-to-docx
title: Convert CMX to DOCX
description: "CMX format represents Corel Metafile Exchange Image File with .cmx extension. Learn how to convert CMX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CMX to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CMX to DOCX in C#
    appDescription: Convert CMX to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CMX to DOCX in C# 
        description: Some description
        url: conversion/net/convert/cmx-to-docx/#steps-to-convert-cmx-to-docx-in-c
        steps:
        - name: Load source CMX file 
          text: Create an instance of Converter class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with CMX extension are Corel Exchange image file format (also known as Corel Metafile Exchange) that is used as presentation by CorelSuite applications. It contains image data as vector graphics as well as metadata that describes the image. CMX files can be opened by CorelDraw, Corel Presentations, Paint Shop Pro and some versions of Adobe Illustrator. CMX files can be converted to other formats such as JPG and EPS.

## Steps to convert CMX to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CMX file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CMX file
using (var converter = new GroupDocs.Conversion.Converter("sample.cmx"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CMX to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**CMX to DOCX converter**](https://products.groupdocs.app/conversion/cmx-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CMX to DOCX"](conversion/net/images/convert-to-docx/convert-cmx-to-docx.png)](https://products.groupdocs.app/conversion/cmx-to-docx)