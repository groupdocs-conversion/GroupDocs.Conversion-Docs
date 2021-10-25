---
id: ods-to-pptx
url: conversion/net/convert/ods-to-pptx
title: Convert ODS to PPTX
description: "ODS format represents Open Document Spreadsheet with .ods extension. Learn how to convert ODS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODS to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ODS to PPTX in C#
    appDescription: Convert ODS to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ODS to PPTX in C# 
        description: Quick guide about how to convert ODS to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/ods-to-pptx/#steps-to-convert-ods-to-pptx-in-c
        steps:
        - name: Load source ODS file 
          text: Create an instance of Converter class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with ODS extension stand for OpenDocument Spreadsheet Document format that is editable by the user. Data is stored inside the ODF file into rows and columns. It is an XML-based format and is one of the several subtypes in the Open Document Formats (ODF) family. The format is specified as part of the ODF 1.2 specifications published and maintained by OASIS.

## Steps to convert ODS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ods"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**ODS to PPTX converter**](https://products.groupdocs.app/conversion/ods-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODS to PPTX"](conversion/net/images/convert-to-pptx/convert-ods-to-pptx.png)](https://products.groupdocs.app/conversion/ods-to-pptx)