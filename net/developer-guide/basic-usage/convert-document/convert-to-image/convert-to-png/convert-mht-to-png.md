---
id: convert-mht-to-png
url: conversion/net/convert-mht-to-png
title: Convert MHT to PNG
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MHT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (Converter converter = new Converter("sample.mht"))
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

### MHT to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to PNG converter**](https://products.groupdocs.app/conversion/mht-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to PNG"](conversion/net/images/convert-to-png/convert-mht-to-png.png)](https://products.groupdocs.app/conversion/mht-to-png)