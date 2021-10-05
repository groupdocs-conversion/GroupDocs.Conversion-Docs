---
id: convert-vtx-to-jpg
url: conversion/net/convert-vtx-to-jpg
title: Convert VTX to JPG
description: "VTX format represents Microsoft Visio Drawing Template with .vtx extension. Learn how to convert VTX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VTX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

## Steps to convert VTX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VTX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source VTX file
using (Converter converter = new Converter("sample.vtx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VTX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**VTX to JPG converter**](https://products.groupdocs.app/conversion/vtx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VTX to JPG"](conversion/net/images/convert-to-jpg/convert-vtx-to-jpg.png)](https://products.groupdocs.app/conversion/vtx-to-jpg)