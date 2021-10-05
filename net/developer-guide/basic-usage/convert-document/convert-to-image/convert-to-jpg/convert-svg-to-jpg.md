---
id: convert-svg-to-jpg
url: conversion/net/convert-svg-to-jpg
title: Convert SVG to JPG
description: "SVG format represents Scalable Vector Graphics File with .svg extension. Learn how to convert SVG to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVG to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

SVG files are Scalable Vector Graphics Files that use XML based text format for describing the appearance of image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text based description of such files make them independent of resolution. It is one of the mostly used format for building website and print graphics in order to achieve scalability.

## Steps to convert SVG to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVG file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source SVG file
using (Converter converter = new Converter("sample.svg"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVG to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**SVG to JPG converter**](https://products.groupdocs.app/conversion/svg-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVG to JPG"](conversion/net/images/convert-to-jpg/convert-svg-to-jpg.png)](https://products.groupdocs.app/conversion/svg-to-jpg)