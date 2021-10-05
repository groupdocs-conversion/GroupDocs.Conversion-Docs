---
id: convert-odp-to-jpg
url: conversion/net/convert-odp-to-jpg
title: Convert ODP to JPG
description: "ODP format represents OpenDocument Presentation File Format with .odp extension. Learn how to convert ODP to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODP to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

## Steps to convert ODP to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODP file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source ODP file
using (Converter converter = new Converter("sample.odp"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODP to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**ODP to JPG converter**](https://products.groupdocs.app/conversion/odp-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODP to JPG"](conversion/net/images/convert-to-jpg/convert-odp-to-jpg.png)](https://products.groupdocs.app/conversion/odp-to-jpg)