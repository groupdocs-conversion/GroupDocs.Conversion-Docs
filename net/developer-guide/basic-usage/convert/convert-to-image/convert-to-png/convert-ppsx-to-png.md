---
id: convert-ppsx-to-png
url: conversion/net/convert-ppsx-to-png
title: Convert PPSX to PNG
description: "PPSX format represents PowerPoint Open XML Slide Show with .ppsx extension. Learn how to convert PPSX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PPSX, Power Point Slide Show, file are created using Microsoft PowerPoint 2007 and above for Slide Show purpose. It is an update to the PPS file format that was supported by Microsoft PowerPoint 97-2003 versions. When a PPSX file is shared with another user and opened, it starts as PowerPoint show unlike PPTX file that opens in editable mode. The sequence of slide show is the same as in the original presentation. All the slides accompany the images, sounds and other embedded media accompany the presentation slides to the PPSX during the slideshow. 

## Steps to convert PPSX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPSX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPSX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPSX file
using (Converter converter = new Converter("sample.ppsx"))
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

### PPSX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSX to PNG converter**](https://products.groupdocs.app/conversion/ppsx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSX to PNG"](conversion/net/images/convert-to-png/convert-ppsx-to-png.png)](https://products.groupdocs.app/conversion/ppsx-to-png)