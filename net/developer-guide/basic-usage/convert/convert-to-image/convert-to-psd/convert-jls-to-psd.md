---
id: convert-jls-to-psd
url: conversion/net/convert-jls-to-psd
title: Convert JLS to PSD
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

## Steps to convert JLS to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JLS file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JLS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JLS file
using (Converter converter = new Converter("sample.jls"))
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

### JLS to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to PSD converter**](https://products.groupdocs.app/conversion/jls-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to PSD"](conversion/net/images/convert-to-psd/convert-jls-to-psd.png)](https://products.groupdocs.app/conversion/jls-to-psd)