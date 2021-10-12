---
id: vst-to-png
url: conversion/net/convert/vst-to-png
title: Convert VST to PNG
description: "VST format represents Visio Drawing Template with .vst extension. Learn how to convert VST to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VST to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VST extension are vector image files created with Microsoft Visio and act as templates for creating further files. These template files are in binary file format and contain the default layout and settings that are utilized for the creation of new Visio drawings. When a VST file is opened in Microsoft Visio, it contains the existing settings to continue working with the document. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VST to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VST file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VST document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VST file
using (Converter converter = new Converter("sample.vst"))
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

### VST to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**VST to PNG converter**](https://products.groupdocs.app/conversion/vst-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VST to PNG"](conversion/net/images/convert-to-png/convert-vst-to-png.png)](https://products.groupdocs.app/conversion/vst-to-png)