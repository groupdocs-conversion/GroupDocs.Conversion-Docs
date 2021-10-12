---
id: convert-vss-to-png
url: conversion/net/convert-vss-to-png
title: Convert VSS to PNG
description: "VSS format represents Visio Stencil File with .vss extension. Learn how to convert VSS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSS is stencil files created with Microsoft Visio 2007 and earlier. A relatively new file format is VSSX that was introduced with Microsoft Visio 2013. Stencil files provide drawing objects that can be included in a VSD Visio drawing. Microsoft Visio is used for creating drawing elements such as a collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping, and other similar information.

## Steps to convert VSS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSS file
using (Converter converter = new Converter("sample.vss"))
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

### VSS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSS to PNG converter**](https://products.groupdocs.app/conversion/vss-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSS to PNG"](conversion/net/images/convert-to-png/convert-vss-to-png.png)](https://products.groupdocs.app/conversion/vss-to-png)