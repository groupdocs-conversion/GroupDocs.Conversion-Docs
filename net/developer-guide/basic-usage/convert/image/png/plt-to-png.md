---
id: plt-to-png
url: conversion/net/convert/plt-to-png
title: Convert PLT to PNG
description: "PLT format represents PLT (HPGL) with .plt extension. Learn how to convert PLT to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PLT to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An HPGL(Hewlett-Packard Graphics Language) file contains an instruction set for plotter control, developed by Hewlett-Packard. Hewlett-Packard plotters use this file to draw and print vector and raster content on the paper.

## Steps to convert PLT to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PLT file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PLT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PLT file
using (Converter converter = new Converter("sample.plt"))
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

### PLT to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PLT to PNG converter**](https://products.groupdocs.app/conversion/plt-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PLT to PNG"](conversion/net/images/convert-to-png/convert-plt-to-png.png)](https://products.groupdocs.app/conversion/plt-to-png)