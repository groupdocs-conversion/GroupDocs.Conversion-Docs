---
id: cdr-to-psd
url: conversion/net/convert/cdr-to-psd
title: Convert CDR to PSD
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to PSD in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CDR to PSD in C#
    appDescription: Convert CDR to PSD natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CDR to PSD in C# 
        description: Some description
        url: conversion/net/convert/cdr-to-psd/#steps-to-convert-cdr-to-psd-in-c
        steps:
        - name: Load source CDR file 
          text: Create an instance of Converter class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PSD and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

## Steps to convert CDR to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CDR file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of CDR document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CDR file
using (Converter converter = new Converter("sample.cdr"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CDR to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to PSD converter**](https://products.groupdocs.app/conversion/cdr-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to PSD"](conversion/net/images/convert-to-psd/convert-cdr-to-psd.png)](https://products.groupdocs.app/conversion/cdr-to-psd)