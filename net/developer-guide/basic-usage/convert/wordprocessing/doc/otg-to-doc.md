---
id: otg-to-doc
url: conversion/net/convert/otg-to-doc
title: Convert OTG to DOC
description: "OTG format represents OpenDocument Graphic Template with .otg extension. Learn how to convert OTG to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTG to DOC in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert OTG to DOC in C#
    appDescription: Convert OTG to DOC natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert OTG to DOC in C# 
        description: Quick guide about how to convert OTG to DOC in C# with high performance and accuracy.
        url: conversion/net/convert/otg-to-doc/#steps-to-convert-otg-to-doc-in-c
        steps:
        - name: Load source OTG file 
          text: Create an instance of Converter class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

An OTG file is a drawing template that is created using the OpenDocument standard that follows the OASIS Office Applications 1.0 specification. It represents the default organization of drawing elements for a vector image that can be used to further enhance the contents of the file.

## Steps to convert OTG to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTG file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTG file
using (var converter = new GroupDocs.Conversion.Converter("sample.otg"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTG to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**OTG to DOC converter**](https://products.groupdocs.app/conversion/otg-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTG to DOC"](conversion/net/images/convert-to-doc/convert-otg-to-doc.png)](https://products.groupdocs.app/conversion/otg-to-doc)