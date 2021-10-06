---
id: convert-pcl-to-png
url: conversion/net/convert-pcl-to-png
title: Convert PCL to PNG
description: "PCL format represents Printer Command Language Document with .pcl extension. Learn how to convert PCL to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PCL to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PCL stands for Printer Command Language which is a Page Description Language introduced by Hewlett Packard (HP). HP created PCL to provide an efficient way of controlling printer features across many different printing devices. The format was originally developed for HP’s dot-matrix and Inkjet printers but has been part of various thermal, matrix, and page printers with the passage of time. The format underwent several different revisions, resulting in different versions where each version was enhanced to meet the demands of time with respect to the printer control features

## Steps to convert PCL to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PCL file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PCL file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PCL document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PCL file
using (Converter converter = new Converter("sample.pcl"))
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

### PCL to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PCL to PNG converter**](https://products.groupdocs.app/conversion/pcl-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PCL to PNG"](conversion/net/images/convert-to-png/convert-pcl-to-png.png)](https://products.groupdocs.app/conversion/pcl-to-png)