---
id: potx-to-pptx
url: conversion/net/convert/potx-to-pptx
title: Convert POTX to PPTX
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert POTX to PPTX in C#
    appDescription: Convert POTX to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert POTX to PPTX in C# 
        description: Some description
        url: conversion/net/convert/potx-to-pptx/#steps-to-convert-potx-to-pptx-in-c
        steps:
        - name: Load source POTX file 
          text: Create an instance of Converter class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

## Steps to convert POTX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.potx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to PPTX converter**](https://products.groupdocs.app/conversion/potx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to PPTX"](conversion/net/images/convert-to-pptx/convert-potx-to-pptx.png)](https://products.groupdocs.app/conversion/potx-to-pptx)