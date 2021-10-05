---
id: convert-vstx-to-jpg
url: conversion/net/convert-vstx-to-jpg
title: Convert VSTX to JPG
description: "VSTX format represents Microsoft Visio File Format with .vstx extension. Learn how to convert VSTX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSTX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with VSTX extensions are drawing template files created with Microsoft Visio 2013 and above. These VSTX files provide a starting point for creating Visio drawings, saved as VSDX files, with default layout and settings. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

## Steps to convert VSTX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSTX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source VSTX file
using (Converter converter = new Converter("sample.vstx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSTX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSTX to JPG converter**](https://products.groupdocs.app/conversion/vstx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSTX to JPG"](conversion/net/images/convert-to-jpg/convert-vstx-to-jpg.png)](https://products.groupdocs.app/conversion/vstx-to-jpg)