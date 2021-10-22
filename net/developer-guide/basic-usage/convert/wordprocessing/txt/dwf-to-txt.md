---
id: dwf-to-txt
url: conversion/net/convert/dwf-to-txt
title: Convert DWF to TXT
description: "DWF format represents Design Web Format with .dwf extension. Learn how to convert DWF to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWF to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DWF to TXT in C#
    appDescription: Convert DWF to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DWF to TXT in C# 
        description: Some description
        url: conversion/net/convert/dwf-to-txt/#steps-to-convert-dwf-to-txt-in-c
        steps:
        - name: Load source DWF file 
          text: Create an instance of Converter class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing, or printing design files. It contains graphics and text as part of design data and reduces the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn't require the recipient to know about the usage of CAD software that created the original drawing.

## Steps to convert DWF to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWF file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwf"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWF to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DWF to TXT converter**](https://products.groupdocs.app/conversion/dwf-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWF to TXT"](conversion/net/images/convert-to-txt/convert-dwf-to-txt.png)](https://products.groupdocs.app/conversion/dwf-to-txt)