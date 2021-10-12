---
id: convert-jpm-to-jpg
url: conversion/net/convert-jpm-to-jpg
title: Convert JPM to JPG
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JPM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (Converter converter = new Converter("sample.jpm"))
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

### JPM to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to JPG converter**](https://products.groupdocs.app/conversion/jpm-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to JPG"](conversion/net/images/convert-to-jpg/convert-jpm-to-jpg.png)](https://products.groupdocs.app/conversion/jpm-to-jpg)