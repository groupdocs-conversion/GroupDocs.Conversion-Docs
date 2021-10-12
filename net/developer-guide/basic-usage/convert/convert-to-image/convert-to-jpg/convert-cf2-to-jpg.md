---
id: convert-cf2-to-jpg
url: conversion/net/convert-cf2-to-jpg
title: Convert CF2 to JPG
description: "CF2 format represents Common File Format File with .cf2 extension. Learn how to convert CF2 to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CF2 to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .cf2 extension is a CAD file format that contains 3D package designs or other model data for die-cutting. Most of the CAD/CAM machines can process and cut these files. It was created by the National Space Science Data Center (NSSDC) to provide self-describing data storage and manipulation format that matches the structure of scientific data and applications such as statistical and numerical methods, visualization, and management. 

## Steps to convert CF2 to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CF2 file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CF2 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of CF2 document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CF2 file
using (Converter converter = new Converter("sample.cf2"))
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

### CF2 to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**CF2 to JPG converter**](https://products.groupdocs.app/conversion/cf2-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CF2 to JPG"](conversion/net/images/convert-to-jpg/convert-cf2-to-jpg.png)](https://products.groupdocs.app/conversion/cf2-to-jpg)