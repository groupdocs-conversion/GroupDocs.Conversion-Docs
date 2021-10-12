---
id: j2c-to-jpg
url: conversion/net/convert/j2c-to-jpg
title: Convert J2C to JPG
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of J2C document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (Converter converter = new Converter("sample.j2c"))
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

### J2C to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to JPG converter**](https://products.groupdocs.app/conversion/j2c-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to JPG"](conversion/net/images/convert-to-jpg/convert-j2c-to-jpg.png)](https://products.groupdocs.app/conversion/j2c-to-jpg)