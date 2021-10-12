---
id: jpg-to-png
url: conversion/net/convert/jpg-to-png
title: Convert JPG to PNG
description: "JPG format represents Joint Photographic Expert Group Image File with .jpg extension. Learn how to convert JPG to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPG to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

## Steps to convert JPG to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPG file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JPG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPG file
using (Converter converter = new Converter("sample.jpg"))
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

### JPG to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPG to PNG converter**](https://products.groupdocs.app/conversion/jpg-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPG to PNG"](conversion/net/images/convert-to-png/convert-jpg-to-png.png)](https://products.groupdocs.app/conversion/jpg-to-png)