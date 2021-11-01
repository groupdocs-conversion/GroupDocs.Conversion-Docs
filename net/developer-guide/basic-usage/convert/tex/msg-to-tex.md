---
id: msg-to-tex
url: conversion/net/convert/msg-to-tex
title: Convert MSG to TEX
description: "MSG format represents Microsoft Outlook Email Format with .msg extension. Learn how to convert MSG to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MSG to TEX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MSG to TEX in C#
    appDescription: Convert MSG to TEX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MSG to TEX in C# 
        description: Quick guide about how to convert MSG to TEX in C# with high performance and accuracy.
        url: conversion/net/convert/msg-to-tex/#steps-to-convert-msg-to-tex-in-c
        steps:
        - name: Load source MSG file 
          text: Create an instance of Converter class and pass source MSG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

MSG is a file format used by Microsoft Outlook and Exchange to store email messages, contact, appointment, or other tasks. Such messages may contain one or more email fields, with the sender, recipient, subject, date, and message body, or contact information, appointment particulars, and one or more task specifications. The properties that constitute the Message object, including are also a part of the MSG file.

## Steps to convert MSG to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MSG file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MSG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MSG file
using (var converter = new GroupDocs.Conversion.Converter("sample.msg"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MSG to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**MSG to TEX converter**](https://products.groupdocs.app/conversion/msg-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MSG to TEX"](conversion/net/images/convert-to-tex/convert-msg-to-tex.png)](https://products.groupdocs.app/conversion/msg-to-tex)