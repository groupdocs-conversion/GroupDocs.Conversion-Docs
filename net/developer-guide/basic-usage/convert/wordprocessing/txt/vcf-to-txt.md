---
id: vcf-to-txt
url: conversion/net/convert/vcf-to-txt
title: Convert VCF to TXT
description: "VCF format represents vCard File with .vcf extension. Learn how to convert VCF to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VCF to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert VCF to TXT in C#
    appDescription: Convert VCF to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert VCF to TXT in C# 
        description: Some description
        url: conversion/net/convert/vcf-to-txt/#steps-to-convert-vcf-to-txt-in-c
        steps:
        - name: Load source VCF file 
          text: Create an instance of Converter class and pass source VCF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

VCF (Virtual Card Format) or vCard is a digital file format for storing contact information. The format is widely used for data interchange among popular information exchange applications. Most operating systems such as Windows and macOS come with default applications to create and open these files. A single VCF file can contain contact information for one or multiple contacts.

## Steps to convert VCF to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VCF file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VCF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VCF file
using (var converter = new GroupDocs.Conversion.Converter("sample.vcf"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VCF to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**VCF to TXT converter**](https://products.groupdocs.app/conversion/vcf-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VCF to TXT"](conversion/net/images/convert-to-txt/convert-vcf-to-txt.png)](https://products.groupdocs.app/conversion/vcf-to-txt)