---
id: ots-to-pptx
url: conversion/net/convert/ots-to-pptx
title: Convert OTS to PPTX
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to PPTX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert OTS to PPTX in C#
    appDescription: Convert OTS to PPTX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert OTS to PPTX in C# 
        description: Quick guide about how to convert OTS to PPTX in C# with high performance and accuracy.
        url: conversion/net/convert/ots-to-pptx/#steps-to-convert-ots-to-pptx-in-c
        steps:
        - name: Load source OTS file 
          text: Create an instance of Converter class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

## Steps to convert OTS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ots"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to PPTX converter**](https://products.groupdocs.app/conversion/ots-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to PPTX"](conversion/net/images/convert-to-pptx/convert-ots-to-pptx.png)](https://products.groupdocs.app/conversion/ots-to-pptx)