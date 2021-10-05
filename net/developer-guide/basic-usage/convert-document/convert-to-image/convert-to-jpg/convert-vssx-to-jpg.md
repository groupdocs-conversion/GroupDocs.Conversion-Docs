---
id: convert-vssx-to-jpg
url: conversion/net/convert-vssx-to-jpg
title: Convert VSSX to JPG
description: "VSSX format represents Visio Stencil File Format with .vssx extension. Learn how to convert VSSX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

## Steps to convert VSSX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source VSSX file
using (Converter converter = new Converter("sample.vssx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSSX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSX to JPG converter**](https://products.groupdocs.app/conversion/vssx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSX to JPG"](conversion/net/images/convert-to-jpg/convert-vssx-to-jpg.png)](https://products.groupdocs.app/conversion/vssx-to-jpg)