---
id: j2k-to-jpg
url: conversion/net/convert/j2k-to-jpg
title: Convert J2K to JPG
description: "J2K format represents JPEG 2000 Image with .j2k extension. Learn how to convert J2K to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2K to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2K file is an image that is compressed using the wavelet compression instead of DCT compression.

## Steps to convert J2K to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2K file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2K file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of J2K document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2K file
using (Converter converter = new Converter("sample.j2k"))
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

### J2K to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**J2K to JPG converter**](https://products.groupdocs.app/conversion/j2k-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2K to JPG"](conversion/net/images/convert-to-jpg/convert-j2k-to-jpg.png)](https://products.groupdocs.app/conversion/j2k-to-jpg)