---
id: convert-emlx-to-jpg
url: conversion/net/convert-emlx-to-jpg
title: Convert EMLX to JPG
description: "EMLX format represents Apple Mail Message with .emlx extension. Learn how to convert EMLX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMLX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The EMLX file format is implemented and developed by Apple. The Apple Mail application uses the EMLX file format for exporting the emails. There are other applications as well such as GroupDocs.Conversion App that can open the EMLX files and convert these to other file formats.

## Steps to convert EMLX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMLX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMLX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source EMLX file
using (Converter converter = new Converter("sample.emlx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMLX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMLX to JPG converter**](https://products.groupdocs.app/conversion/emlx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMLX to JPG"](conversion/net/images/convert-to-jpg/convert-emlx-to-jpg.png)](https://products.groupdocs.app/conversion/emlx-to-jpg)