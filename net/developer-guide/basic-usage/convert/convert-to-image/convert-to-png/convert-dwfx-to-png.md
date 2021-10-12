---
id: convert-dwfx-to-png
url: conversion/net/convert-dwfx-to-png
title: Convert DWFX to PNG
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWFX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (Converter converter = new Converter("sample.dwfx"))
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

### DWFX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to PNG converter**](https://products.groupdocs.app/conversion/dwfx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to PNG"](conversion/net/images/convert-to-png/convert-dwfx-to-png.png)](https://products.groupdocs.app/conversion/dwfx-to-png)