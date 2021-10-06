---
id: convert-mobi-to-png
url: conversion/net/convert-mobi-to-png
title: Convert MOBI to PNG
description: "MOBI format represents Mobipocket eBook with .mobi extension. Learn how to convert MOBI to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MOBI to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The MOBI file format is one of the most widely used ebook file formats. The format is an enhancement to the old OEB (Open Ebook Format) format and was used as the proprietary format for Mobipocket Reader. Like EPUB, it is supported by almost all modern e-readers specifically by mobile devices with low bandwidth. The format can be converted to several other formats such as PDF, EPUB, and several other formats using publicly available software applications such as the Kindle app.

## Steps to convert MOBI to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MOBI file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MOBI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MOBI document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MOBI file
using (Converter converter = new Converter("sample.mobi"))
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

### MOBI to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**MOBI to PNG converter**](https://products.groupdocs.app/conversion/mobi-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MOBI to PNG"](conversion/net/images/convert-to-png/convert-mobi-to-png.png)](https://products.groupdocs.app/conversion/mobi-to-png)