---
id: convert-svgz-to-jpg
url: conversion/net/convert-svgz-to-jpg
title: Convert SVGZ to JPG
description: "SVGZ format represents Compressed Scalable Vector Graphics File with .svgz extension. Learn how to convert SVGZ to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVGZ to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .svgz extension is a compressed version of Scalable Vector Graphics (.SVG) file. It is compressed with gzip compression and contains data in XML format. SVGZ files support transparency, gradients, animations, and filters. SVGZ files are smaller in size as compared to the default SVG files and this reduced file size helps transfer the graphics files.

## Steps to convert SVGZ to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVGZ file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVGZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of SVGZ document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVGZ file
using (Converter converter = new Converter("sample.svgz"))
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

### SVGZ to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**SVGZ to JPG converter**](https://products.groupdocs.app/conversion/svgz-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVGZ to JPG"](conversion/net/images/convert-to-jpg/convert-svgz-to-jpg.png)](https://products.groupdocs.app/conversion/svgz-to-jpg)