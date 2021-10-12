---
id: convert-emf-to-png
url: conversion/net/convert-emf-to-png
title: Convert EMF to PNG
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

## Steps to convert EMF to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMF file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EMF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMF file
using (Converter converter = new Converter("sample.emf"))
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

### EMF to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to PNG converter**](https://products.groupdocs.app/conversion/emf-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to PNG"](conversion/net/images/convert-to-png/convert-emf-to-png.png)](https://products.groupdocs.app/conversion/emf-to-png)