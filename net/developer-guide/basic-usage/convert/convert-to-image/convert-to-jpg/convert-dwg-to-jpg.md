---
id: convert-dwg-to-jpg
url: conversion/net/convert-dwg-to-jpg
title: Convert DWG to JPG
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (Converter converter = new Converter("sample.dwg"))
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

### DWG to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to JPG converter**](https://products.groupdocs.app/conversion/dwg-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to JPG"](conversion/net/images/convert-to-jpg/convert-dwg-to-jpg.png)](https://products.groupdocs.app/conversion/dwg-to-jpg)