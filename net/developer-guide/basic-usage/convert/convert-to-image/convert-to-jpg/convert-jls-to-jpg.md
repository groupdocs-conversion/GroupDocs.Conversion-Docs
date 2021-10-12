---
id: convert-jls-to-jpg
url: conversion/net/convert-jls-to-jpg
title: Convert JLS to JPG
description: "JLS format represents JPEG Lossless Image File with .jls extension. Learn how to convert JLS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JLS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JLS file is an image saved in the JPEG-LS file format. It contains a lossy or lossless compressed image. JLS files are typically created by medical imaging devices and digital cameras.

## Steps to convert JLS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JLS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JLS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JLS file
using (Converter converter = new Converter("sample.jls"))
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

### JLS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**JLS to JPG converter**](https://products.groupdocs.app/conversion/jls-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JLS to JPG"](conversion/net/images/convert-to-jpg/convert-jls-to-jpg.png)](https://products.groupdocs.app/conversion/jls-to-jpg)