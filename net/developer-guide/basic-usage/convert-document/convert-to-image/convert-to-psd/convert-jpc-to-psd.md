---
id: convert-jpc-to-psd
url: conversion/net/convert-jpc-to-psd
title: Convert JPC to PSD
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JPC document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (Converter converter = new Converter("sample.jpc"))
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

### JPC to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to PSD converter**](https://products.groupdocs.app/conversion/jpc-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to PSD"](conversion/net/images/convert-to-psd/convert-jpc-to-psd.png)](https://products.groupdocs.app/conversion/jpc-to-psd)