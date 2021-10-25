---
id: odg-to-xls
url: conversion/net/convert/odg-to-xls
title: Convert ODG to XLS
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to XLS in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ODG to XLS in C#
    appDescription: Convert ODG to XLS natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ODG to XLS in C# 
        description: Quick guide about how to convert ODG to XLS in C# with high performance and accuracy.
        url: conversion/net/convert/odg-to-xls/#steps-to-convert-odg-to-xls-in-c
        steps:
        - name: Load source ODG file 
          text: Create an instance of Converter class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to XLS and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the SpreadsheetConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

## Steps to convert ODG to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODG file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODG file
using (var converter = new GroupDocs.Conversion.Converter("sample.odg"))
{
    // Set the convert options for XLS format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODG to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to XLS converter**](https://products.groupdocs.app/conversion/odg-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to XLS"](conversion/net/images/convert-to-xls/convert-odg-to-xls.png)](https://products.groupdocs.app/conversion/odg-to-xls)