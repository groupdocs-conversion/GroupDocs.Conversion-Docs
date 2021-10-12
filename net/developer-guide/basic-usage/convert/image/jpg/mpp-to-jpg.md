---
id: mpp-to-jpg
url: conversion/net/convert/mpp-to-jpg
title: Convert MPP to JPG
description: "MPP format represents Microsoft Project File with .mpp extension. Learn how to convert MPP to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPP to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with MPP extension is Microsoft Project data file that stores information related to project management in an integrated manner. It is proprietary file format developed by Microsoft as file format for Microsoft Project (MSP) which is a project management application software. Besides MPP, MSP supports other file formats as well like project XML schema. Several APIs and applications provide the facility to convert MPP file format to others.

## Steps to convert MPP to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPP file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MPP document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPP file
using (Converter converter = new Converter("sample.mpp"))
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

### MPP to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**MPP to JPG converter**](https://products.groupdocs.app/conversion/mpp-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPP to JPG"](conversion/net/images/convert-to-jpg/convert-mpp-to-jpg.png)](https://products.groupdocs.app/conversion/mpp-to-jpg)