---
id: jpm-to-png
url: conversion/net/convert/jpm-to-png
title: Convert JPM to PNG
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JPM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (Converter converter = new Converter("sample.jpm"))
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

### JPM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to PNG converter**](https://products.groupdocs.app/conversion/jpm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to PNG"](conversion/net/images/convert-to-png/convert-jpm-to-png.png)](https://products.groupdocs.app/conversion/jpm-to-png)