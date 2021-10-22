---
id: emz-to-png
url: conversion/net/convert/emz-to-png
title: Convert EMZ to PNG
description: "EMZ format represents Enhanced Windows Metafile Compressed with .emz extension. Learn how to convert EMZ to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMZ to PNG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert EMZ to PNG in C#
    appDescription: Convert EMZ to PNG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert EMZ to PNG in C# 
        description: Some description
        url: conversion/net/convert/emz-to-png/#steps-to-convert-emz-to-png-in-c
        steps:
        - name: Load source EMZ file 
          text: Create an instance of Converter class and pass source EMZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PNG and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A file with .emz extension is a compressed container of Enhanced Metafile (.emf file). It follows GZIP compression algorithm and takes less storage space due to compression. The small file size makes it more easy to transfer EMZ files over the network.

## Steps to convert EMZ to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMZ file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EMZ document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMZ file
using (Converter converter = new Converter("sample.emz"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMZ to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to PNG converter**](https://products.groupdocs.app/conversion/emz-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to PNG"](conversion/net/images/convert-to-png/convert-emz-to-png.png)](https://products.groupdocs.app/conversion/emz-to-png)