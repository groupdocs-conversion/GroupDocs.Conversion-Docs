---
id: eps-to-png
url: conversion/net/convert/eps-to-png
title: Convert EPS to PNG
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (Converter converter = new Converter("sample.eps"))
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

### EPS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to PNG converter**](https://products.groupdocs.app/conversion/eps-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to PNG"](conversion/net/images/convert-to-png/convert-eps-to-png.png)](https://products.groupdocs.app/conversion/eps-to-png)