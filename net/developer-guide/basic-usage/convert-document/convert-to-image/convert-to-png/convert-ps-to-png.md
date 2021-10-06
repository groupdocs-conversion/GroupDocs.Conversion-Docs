---
id: convert-ps-to-png
url: conversion/net/convert-ps-to-png
title: Convert PS to PNG
description: "PS format represents PostScript (PS) with .ps extension. Learn how to convert PS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straightforward interpretation.

## Steps to convert PS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PS file
using (Converter converter = new Converter("sample.ps"))
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

### PS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PS to PNG converter**](https://products.groupdocs.app/conversion/ps-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PS to PNG"](conversion/net/images/convert-to-png/convert-ps-to-png.png)](https://products.groupdocs.app/conversion/ps-to-png)