---
id: jpeg-to-txt
url: conversion/net/convert/jpeg-to-txt
title: Convert JPEG to TXT
description: "JPEG format represents JPEG Image with .jpeg extension. Learn how to convert JPEG to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPEG to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality. JPEG image file format was standardized by the Joint Photographic Experts Group and, hence, the name JPEG. The format has been the choice of storing and transmitting photographic images on the web. Almost all Operating systems now have viewers that support visualization of JPEG images, which are often stored with JPG extension as well. Even the web browsers support visualization of JPEG images.

## Steps to convert JPEG to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPEG file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPEG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`.
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPEG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpeg"))
{
    // Set the convert options for TXT format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPEG to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**JPEG to TXT converter**](https://products.groupdocs.app/conversion/jpeg-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPEG to TXT"](conversion/net/images/convert-to-txt/convert-jpeg-to-txt.png)](https://products.groupdocs.app/conversion/jpeg-to-txt)