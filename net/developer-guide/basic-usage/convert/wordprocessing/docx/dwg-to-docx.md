---
id: dwg-to-docx
url: conversion/net/convert/dwg-to-docx
title: Convert DWG to DOCX
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWG to DOCX in C#
    appDescription: Convert DWG to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWG to DOCX in C# 
        description: Some description
        url: conversion/net/convert/dwg-to-docx/#steps-to-convert-dwg-to-docx-in-c
        steps:
        - name: Load source DWG file 
          text: Create an instance of Converter class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to DOCX converter**](https://products.groupdocs.app/conversion/dwg-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to DOCX"](conversion/net/images/convert-to-docx/convert-dwg-to-docx.png)](https://products.groupdocs.app/conversion/dwg-to-docx)