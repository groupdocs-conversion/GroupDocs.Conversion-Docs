---
id: potm-to-tex
url: conversion/net/convert/potm-to-tex
title: Convert POTM to TEX
description: "POTM format represents Microsoft PowerPoint Template with .potm extension. Learn how to convert POTM to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTM to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert POTM to TEX in C#
    appDescription: Convert POTM to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert POTM to TEX in C# 
        description: Some description
        url: conversion/net/convert/potm-to-tex/#steps-to-convert-potm-to-tex-in-c
        steps:
        - name: Load source POTM file 
          text: Create an instance of Converter class and pass source POTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TEX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PdfConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with POTM extension are Microsoft PowerPoint template files with support for Macros. POTM files are created with PowerPoint 2007 or above and contains default settings that can be used to create further presentation files. These settings can include styles, backgrounds, colour palette, fonts and defaults along with macros that consist of custom functions for doing particular task. They may also be opened by a previous version of PowerPoint with Open XML document support installed. POTM files can be opened in Microsoft PowerPoint for editing like any other PowerPoint file.

## Steps to convert POTM to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTM file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.potm"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTM to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**POTM to TEX converter**](https://products.groupdocs.app/conversion/potm-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTM to TEX"](conversion/net/images/convert-to-tex/convert-potm-to-tex.png)](https://products.groupdocs.app/conversion/potm-to-tex)