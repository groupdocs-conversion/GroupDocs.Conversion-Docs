---
id: convert-ps-to-jpg
url: conversion/net/convert-ps-to-jpg
title: Convert PS to JPG
description: "PS format represents PostScript (PS) with .ps extension. Learn how to convert PS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straightforward interpretation.

## Steps to convert PS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PS file
using (Converter converter = new Converter("sample.ps"))
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

### PS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**PS to JPG converter**](https://products.groupdocs.app/conversion/ps-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PS to JPG"](conversion/net/images/convert-to-jpg/convert-ps-to-jpg.png)](https://products.groupdocs.app/conversion/ps-to-jpg)