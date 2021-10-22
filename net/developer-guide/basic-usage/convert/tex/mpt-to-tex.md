---
id: mpt-to-tex
url: conversion/net/convert/mpt-to-tex
title: Convert MPT to TEX
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MPT to TEX in C#
    appDescription: Convert MPT to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MPT to TEX in C# 
        description: Some description
        url: conversion/net/convert/mpt-to-tex/#steps-to-convert-mpt-to-tex-in-c
        steps:
        - name: Load source MPT file 
          text: Create an instance of Converter class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpt"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPT to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to TEX converter**](https://products.groupdocs.app/conversion/mpt-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to TEX"](conversion/net/images/convert-to-tex/convert-mpt-to-tex.png)](https://products.groupdocs.app/conversion/mpt-to-tex)