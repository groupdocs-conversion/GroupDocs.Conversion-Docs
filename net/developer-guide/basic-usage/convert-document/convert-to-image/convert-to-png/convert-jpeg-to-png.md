---
id: convert-jpeg-to-png
url: conversion/net/convert-jpeg-to-png
title: Convert JPEG to PNG
description: "JPEG format represents JPEG Image with .jpeg extension. Learn how to convert JPEG to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPEG to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality. JPEG image file format was standardized by the Joint Photographic Experts Group and, hence, the name JPEG. The format has been the choice of storing and transmitting photographic images on the web. Almost all Operating systems now have viewers that support visualization of JPEG images, which are often stored with JPG extension as well. Even the web browsers support visualization of JPEG images.

## Steps to convert JPEG to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPEG file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPEG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of JPEG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPEG file
using (Converter converter = new Converter("sample.jpeg"))
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

### JPEG to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPEG to PNG converter**](https://products.groupdocs.app/conversion/jpeg-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPEG to PNG"](conversion/net/images/convert-to-png/convert-jpeg-to-png.png)](https://products.groupdocs.app/conversion/jpeg-to-png)