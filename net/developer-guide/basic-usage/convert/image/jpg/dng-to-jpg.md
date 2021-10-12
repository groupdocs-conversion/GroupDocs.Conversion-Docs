---
id: dng-to-jpg
url: conversion/net/convert/dng-to-jpg
title: Convert DNG to JPG
description: "DNG format represents Digital Camera Image Format with .dng extension. Learn how to convert DNG to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DNG to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DNG is a digital camera image format used for the storage of raw files. It has been developed by Adobe in September 2004. It was basically developed for digital photography. DNG is an extension of TIFF/EP standard format and uses metadata significantly. In order to manipulate raw data from digital cameras with ease of flexibility and artistic control, photographers opt camera raw files.

## Steps to convert DNG to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DNG file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DNG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DNG file
using (Converter converter = new Converter("sample.dng"))
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

### DNG to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DNG to JPG converter**](https://products.groupdocs.app/conversion/dng-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DNG to JPG"](conversion/net/images/convert-to-jpg/convert-dng-to-jpg.png)](https://products.groupdocs.app/conversion/dng-to-jpg)