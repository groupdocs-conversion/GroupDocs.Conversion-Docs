---
id: convert-vst-to-ppt
url: conversion/net/convert-vst-to-ppt
title: Convert VST to PPT
description: "VST format represents Visio Drawing Template with .vst extension. Learn how to convert VST to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VST to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VST extension are vector image files created with Microsoft Visio and act as templates for creating further files. These template files are in binary file format and contain the default layout and settings that are utilized for the creation of new Visio drawings. When a VST file is opened in Microsoft Visio, it contains the existing settings to continue working with the document. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VST to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VST file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VST file
using (var converter = new GroupDocs.Conversion.Converter("sample.vst"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VST to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**VST to PPT converter**](https://products.groupdocs.app/conversion/vst-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VST to PPT"](conversion/net/images/convert-to-ppt/convert-vst-to-ppt.png)](https://products.groupdocs.app/conversion/vst-to-ppt)