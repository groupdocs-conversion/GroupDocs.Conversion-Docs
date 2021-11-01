---
id: log-to-psd
url: conversion/net/convert/log-to-psd
title: Convert LOG to PSD
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to PSD in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert LOG to PSD in C#
    appDescription: Convert LOG to PSD natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert LOG to PSD in C# 
        description: Quick guide about how to convert LOG to PSD in C# with high performance and accuracy.
        url: conversion/net/convert/log-to-psd/#steps-to-convert-log-to-psd-in-c
        steps:
        - name: Load source LOG file 
          text: Create an instance of Converter class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of LOG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (Converter converter = new Converter("sample.log"))
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

### LOG to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to PSD converter**](https://products.groupdocs.app/conversion/log-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to PSD"](conversion/net/images/convert-to-psd/convert-log-to-psd.png)](https://products.groupdocs.app/conversion/log-to-psd)