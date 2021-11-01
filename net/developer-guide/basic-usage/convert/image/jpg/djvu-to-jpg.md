---
id: djvu-to-jpg
url: conversion/net/convert/djvu-to-jpg
title: Convert DJVU to JPG
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to JPG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert DJVU to JPG in C#
    appDescription: Convert DJVU to JPG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert DJVU to JPG in C# 
        description: Quick guide about how to convert DJVU to JPG in C# with high performance and accuracy.
        url: conversion/net/convert/djvu-to-jpg/#steps-to-convert-djvu-to-jpg-in-c
        steps:
        - name: Load source DJVU file 
          text: Create an instance of Converter class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to JPG and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DJVU document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (Converter converter = new Converter("sample.djvu"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to JPG converter**](https://products.groupdocs.app/conversion/djvu-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to JPG"](conversion/net/images/convert-to-jpg/convert-djvu-to-jpg.png)](https://products.groupdocs.app/conversion/djvu-to-jpg)