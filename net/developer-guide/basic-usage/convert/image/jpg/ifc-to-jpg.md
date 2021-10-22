---
id: ifc-to-jpg
url: conversion/net/convert/ifc-to-jpg
title: Convert IFC to JPG
description: "IFC format represents Industry Foundation Classes (IFC) File Format with .ifc extension. Learn how to convert IFC to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IFC to JPG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert IFC to JPG in C#
    appDescription: Convert IFC to JPG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert IFC to JPG in C# 
        description: Some description
        url: conversion/net/convert/ifc-to-jpg/#steps-to-convert-ifc-to-jpg-in-c
        steps:
        - name: Load source IFC file 
          text: Create an instance of Converter class and pass source IFC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
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

Files with IFC extension refer to  Industry Foundation Classes (IFC) file format that establishes international standards to import and export building objects and their properties. This file format provides interoperability between different software applications. Specifications for this file format are developed and maintained by buildingSMART International as its Data Standard.

## Steps to convert IFC to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IFC file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IFC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of IFC document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IFC file
using (Converter converter = new Converter("sample.ifc"))
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

### IFC to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**IFC to JPG converter**](https://products.groupdocs.app/conversion/ifc-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IFC to JPG"](conversion/net/images/convert-to-jpg/convert-ifc-to-jpg.png)](https://products.groupdocs.app/conversion/ifc-to-jpg)