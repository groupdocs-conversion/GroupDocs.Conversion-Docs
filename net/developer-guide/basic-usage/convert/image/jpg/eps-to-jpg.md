---
id: eps-to-jpg
url: conversion/net/convert/eps-to-jpg
title: Convert EPS to JPG
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (Converter converter = new Converter("sample.eps"))
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

### EPS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to JPG converter**](https://products.groupdocs.app/conversion/eps-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to JPG"](conversion/net/images/convert-to-jpg/convert-eps-to-jpg.png)](https://products.groupdocs.app/conversion/eps-to-jpg)