---
id: convert-emf-to-jpg
url: conversion/net/convert-emf-to-jpg
title: Convert EMF to JPG
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

## Steps to convert EMF to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMF file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source EMF file
using (Converter converter = new Converter("sample.emf"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMF to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to JPG converter**](https://products.groupdocs.app/conversion/emf-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to JPG"](conversion/net/images/convert-to-jpg/convert-emf-to-jpg.png)](https://products.groupdocs.app/conversion/emf-to-jpg)