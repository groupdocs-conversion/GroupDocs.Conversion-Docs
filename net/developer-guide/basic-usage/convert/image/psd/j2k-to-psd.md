---
id: j2k-to-psd
url: conversion/net/convert/j2k-to-psd
title: Convert J2K to PSD
description: "J2K format represents JPEG 2000 Image with .j2k extension. Learn how to convert J2K to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2K to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2K file is an image that is compressed using the wavelet compression instead of DCT compression.

## Steps to convert J2K to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2K file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2K file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of J2K document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2K file
using (Converter converter = new Converter("sample.j2k"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2K to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**J2K to PSD converter**](https://products.groupdocs.app/conversion/j2k-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2K to PSD"](conversion/net/images/convert-to-psd/convert-j2k-to-psd.png)](https://products.groupdocs.app/conversion/j2k-to-psd)