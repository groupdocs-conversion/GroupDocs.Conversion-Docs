---
id: convert-dwg-to-png
url: conversion/net/convert-dwg-to-png
title: Convert DWG to PNG
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (Converter converter = new Converter("sample.dwg"))
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

### DWG to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to PNG converter**](https://products.groupdocs.app/conversion/dwg-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to PNG"](conversion/net/images/convert-to-png/convert-dwg-to-png.png)](https://products.groupdocs.app/conversion/dwg-to-png)