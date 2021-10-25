---
id: ots-to-doc
url: conversion/net/convert/ots-to-doc
title: Convert OTS to DOC
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to DOC in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert OTS to DOC in C#
    appDescription: Convert OTS to DOC natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert OTS to DOC in C# 
        description: Quick guide about how to convert OTS to DOC in C# with high performance and accuracy.
        url: conversion/net/convert/ots-to-doc/#steps-to-convert-ots-to-doc-in-c
        steps:
        - name: Load source OTS file 
          text: Create an instance of Converter class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOC and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

## Steps to convert OTS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ots"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to DOC converter**](https://products.groupdocs.app/conversion/ots-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to DOC"](conversion/net/images/convert-to-doc/convert-ots-to-doc.png)](https://products.groupdocs.app/conversion/ots-to-doc)