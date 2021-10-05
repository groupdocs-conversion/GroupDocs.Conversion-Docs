---
id: convert-bmp-to-jpg
url: conversion/net/convert-bmp-to-jpg
title: Convert BMP to JPG
description: "BMP format represents Bitmap File Format with .bmp extension. Learn how to convert BMP to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert BMP to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files having extension .BMP represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images  in both monochrome as well as color format with various colour depths.

## Steps to convert BMP to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the BMP file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source BMP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source BMP file
using (Converter converter = new Converter("sample.bmp"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### BMP to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**BMP to JPG converter**](https://products.groupdocs.app/conversion/bmp-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert BMP to JPG"](conversion/net/images/convert-to-jpg/convert-bmp-to-jpg.png)](https://products.groupdocs.app/conversion/bmp-to-jpg)