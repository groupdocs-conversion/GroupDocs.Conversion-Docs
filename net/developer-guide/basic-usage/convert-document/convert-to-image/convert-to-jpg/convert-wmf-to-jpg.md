---
id: convert-wmf-to-jpg
url: conversion/net/convert-wmf-to-jpg
title: Convert WMF to JPG
description: "WMF format represents Windows Metafile with .wmf extension. Learn how to convert WMF to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WMF to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with WMF extension represent Microsoft Windows Metafile (WMF) for storing vector as well as bitmap-format images data. To be more accurate, WMF belongs to the vector file format category of Graphics file formats that is device independent. Windows Graphical Device Interface (GDI) uses the functions stored in a WMF file to display an image on the screen.

## Steps to convert WMF to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WMF file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source WMF file
using (Converter converter = new Converter("sample.wmf"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WMF to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**WMF to JPG converter**](https://products.groupdocs.app/conversion/wmf-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WMF to JPG"](conversion/net/images/convert-to-jpg/convert-wmf-to-jpg.png)](https://products.groupdocs.app/conversion/wmf-to-jpg)