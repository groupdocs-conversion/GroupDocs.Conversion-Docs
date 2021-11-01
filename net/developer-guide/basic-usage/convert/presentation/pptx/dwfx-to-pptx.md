---
id: dwfx-to-pptx
url: conversion/net/convert/dwfx-to-pptx
title: Convert DWFX to PPTX
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWFX to PPTX in C#
    appDescription: Convert DWFX to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWFX to PPTX in C# 
        description: Quick guide about how to convert DWFX to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/dwfx-to-pptx/#steps-to-convert-dwfx-to-pptx-in-c
        steps:
        - name: Load source DWFX file 
          text: Create an instance of Converter class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwfx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWFX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to PPTX converter**](https://products.groupdocs.app/conversion/dwfx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to PPTX"](conversion/net/images/convert-to-pptx/convert-dwfx-to-pptx.png)](https://products.groupdocs.app/conversion/dwfx-to-pptx)