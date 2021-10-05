---
id: convert-eml-to-jpg
url: conversion/net/convert-eml-to-jpg
title: Convert EML to JPG
description: "EML format represents E-Mail Message File with .eml extension. Learn how to convert EML to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EML to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EML file format represents email messages saved using Outlook and other relevant applications. Almost all emailing clients support this file format for its compliance with RFC-822 Internet Message Format Standard. Microsoft Outlook is default software for opening EML message types. EML files can be used for saving to disc as well as sending out to recipients using communication protocols.

## Steps to convert EML to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EML file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source EML file
using (Converter converter = new Converter("sample.eml"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EML to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EML to JPG converter**](https://products.groupdocs.app/conversion/eml-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EML to JPG"](conversion/net/images/convert-to-jpg/convert-eml-to-jpg.png)](https://products.groupdocs.app/conversion/eml-to-jpg)