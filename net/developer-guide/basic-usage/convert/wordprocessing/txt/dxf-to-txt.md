---
id: dxf-to-txt
url: conversion/net/convert/dxf-to-txt
title: Convert DXF to TXT
description: "DXF format represents Autodesk Drawing Exchange File Format with .dxf extension. Learn how to convert DXF to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DXF to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DXF to TXT in C#
    appDescription: Convert DXF to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DXF to TXT in C# 
        description: Some description
        url: conversion/net/convert/dxf-to-txt/#steps-to-convert-dxf-to-txt-in-c
        steps:
        - name: Load source DXF file 
          text: Create an instance of Converter class and pass source DXF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to TXT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

DXF, Drawing Interchange Format, or Drawing Exchange Format, is a tagged data representation of AutoCAD drawing file. Each element in the file has a prefix integer number called a group code. This group code actually represents the element that follows and indicates the meaning of a data element for a given object type. DXF makes it possible to represent almost all user-specified information in a drawing file.

## Steps to convert DXF to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DXF file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DXF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DXF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dxf"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DXF to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DXF to TXT converter**](https://products.groupdocs.app/conversion/dxf-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DXF to TXT"](conversion/net/images/convert-to-txt/convert-dxf-to-txt.png)](https://products.groupdocs.app/conversion/dxf-to-txt)