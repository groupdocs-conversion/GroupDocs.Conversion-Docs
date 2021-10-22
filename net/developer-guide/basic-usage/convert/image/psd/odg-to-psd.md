---
id: odg-to-psd
url: conversion/net/convert/odg-to-psd
title: Convert ODG to PSD
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to PSD in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ODG to PSD in C#
    appDescription: Convert ODG to PSD natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ODG to PSD in C# 
        description: Some description
        url: conversion/net/convert/odg-to-psd/#steps-to-convert-odg-to-psd-in-c
        steps:
        - name: Load source ODG file 
          text: Create an instance of Converter class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

## Steps to convert ODG to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODG file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of ODG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODG file
using (Converter converter = new Converter("sample.odg"))
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

### ODG to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to PSD converter**](https://products.groupdocs.app/conversion/odg-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to PSD"](conversion/net/images/convert-to-psd/convert-odg-to-psd.png)](https://products.groupdocs.app/conversion/odg-to-psd)