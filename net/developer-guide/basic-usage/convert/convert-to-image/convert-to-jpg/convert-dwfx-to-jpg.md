---
id: convert-dwfx-to-jpg
url: conversion/net/convert-dwfx-to-jpg
title: Convert DWFX to JPG
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWFX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (Converter converter = new Converter("sample.dwfx"))
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

### DWFX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWFX to JPG converter**](https://products.groupdocs.app/conversion/dwfx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to JPG"](conversion/net/images/convert-to-jpg/convert-dwfx-to-jpg.png)](https://products.groupdocs.app/conversion/dwfx-to-jpg)