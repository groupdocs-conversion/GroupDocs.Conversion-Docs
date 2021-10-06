---
id: convert-vdw-to-jpg
url: conversion/net/convert-vdw-to-jpg
title: Convert VDW to JPG
description: "VDW format represents Visio Web Drawing with .vdw extension. Learn how to convert VDW to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDW to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VDW is the Visio Graphics Service file format that specifies the streams and storages required for rendering a Web drawing. A web drawing is a collection of drawing pages, shapes, fonts, images, data connections, and diagram update information that can be rendered as a vector or raster drawing. VDW files can be opened in Microsoft Visio as well but are primarily saved for use on the web.

## Steps to convert VDW to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDW file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDW file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VDW document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDW file
using (Converter converter = new Converter("sample.vdw"))
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

### VDW to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**VDW to JPG converter**](https://products.groupdocs.app/conversion/vdw-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDW to JPG"](conversion/net/images/convert-to-jpg/convert-vdw-to-jpg.png)](https://products.groupdocs.app/conversion/vdw-to-jpg)