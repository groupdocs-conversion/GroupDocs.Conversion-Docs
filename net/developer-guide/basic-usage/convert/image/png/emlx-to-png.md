---
id: emlx-to-png
url: conversion/net/convert/emlx-to-png
title: Convert EMLX to PNG
description: "EMLX format represents Apple Mail Message with .emlx extension. Learn how to convert EMLX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMLX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The EMLX file format is implemented and developed by Apple. The Apple Mail application uses the EMLX file format for exporting the emails. There are other applications as well such as GroupDocs.Conversion App that can open the EMLX files and convert these to other file formats.

## Steps to convert EMLX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMLX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMLX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EMLX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMLX file
using (Converter converter = new Converter("sample.emlx"))
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

### EMLX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMLX to PNG converter**](https://products.groupdocs.app/conversion/emlx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMLX to PNG"](conversion/net/images/convert-to-png/convert-emlx-to-png.png)](https://products.groupdocs.app/conversion/emlx-to-png)