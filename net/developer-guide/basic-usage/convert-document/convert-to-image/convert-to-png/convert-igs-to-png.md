---
id: convert-igs-to-png
url: conversion/net/convert-igs-to-png
title: Convert IGS to PNG
description: "IGS format represents Initial Graphics Exchange Specification (IGES) with .igs extension. Learn how to convert IGS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IGS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .igs (Initial Graphics Exchange) extension is a 2D-3D design exchange file format that is independent of source or destination file format specifications used by CAD applications. It is used to exchange design information about circuit diagrams, wireframes, the freeform surfaces between two independent systems. IGS files can be opened by applications such as Autodesk, FreeCAD, CADEX CAD Exchanger, and other similar applications.

## Steps to convert IGS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IGS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IGS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of IGS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IGS file
using (Converter converter = new Converter("sample.igs"))
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

### IGS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**IGS to PNG converter**](https://products.groupdocs.app/conversion/igs-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IGS to PNG"](conversion/net/images/convert-to-png/convert-igs-to-png.png)](https://products.groupdocs.app/conversion/igs-to-png)