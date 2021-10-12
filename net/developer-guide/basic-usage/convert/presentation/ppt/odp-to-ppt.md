---
id: odp-to-ppt
url: conversion/net/convert/odp-to-ppt
title: Convert ODP to PPT
description: "ODP format represents OpenDocument Presentation File Format with .odp extension. Learn how to convert ODP to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODP to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

## Steps to convert ODP to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODP file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.odp"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODP to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**ODP to PPT converter**](https://products.groupdocs.app/conversion/odp-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODP to PPT"](conversion/net/images/convert-to-ppt/convert-odp-to-ppt.png)](https://products.groupdocs.app/conversion/odp-to-ppt)