---
id: sxc-to-txt
url: conversion/net/convert/sxc-to-txt
title: Convert SXC to TXT
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to TXT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert SXC to TXT in C#
    appDescription: Convert SXC to TXT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert SXC to TXT in C# 
        description: Quick guide about how to convert SXC to TXT in C# with high performance and accuracy.
        url: conversion/net/convert/sxc-to-txt/#steps-to-convert-sxc-to-txt-in-c
        steps:
        - name: Load source SXC file 
          text: Create an instance of Converter class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to TXT converter**](https://products.groupdocs.app/conversion/sxc-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to TXT"](conversion/net/images/convert-to-txt/convert-sxc-to-txt.png)](https://products.groupdocs.app/conversion/sxc-to-txt)