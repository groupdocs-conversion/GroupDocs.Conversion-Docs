---
id: convert-vsd-to-png
url: conversion/net/convert-vsd-to-png
title: Convert VSD to PNG
description: "VSD format represents Visio Drawing File Format with .vsd extension. Learn how to convert VSD to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSD to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSD files are drawings created with Microsoft Visio application to represent variety of graphical objects and the interconnection between these. Such drawings can contain visual objects such as visual objects, flow charts, UML diagram, information flow, organizational charts, software diagrams, network layout, database models, objects mapping and other similar information. Microsoft Visio offers the capability to convert Visio files to a number of different file formats including PNG, BMP, PDF and others.

## Steps to convert VSD to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSD file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSD document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSD file
using (Converter converter = new Converter("sample.vsd"))
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

### VSD to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSD to PNG converter**](https://products.groupdocs.app/conversion/vsd-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSD to PNG"](conversion/net/images/convert-to-png/convert-vsd-to-png.png)](https://products.groupdocs.app/conversion/vsd-to-png)