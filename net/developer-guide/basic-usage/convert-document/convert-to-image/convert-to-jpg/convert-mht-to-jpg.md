---
id: convert-mht-to-jpg
url: conversion/net/convert-mht-to-jpg
title: Convert MHT to JPG
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MHT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (Converter converter = new Converter("sample.mht"))
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

### MHT to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to JPG converter**](https://products.groupdocs.app/conversion/mht-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to JPG"](conversion/net/images/convert-to-jpg/convert-mht-to-jpg.png)](https://products.groupdocs.app/conversion/mht-to-jpg)