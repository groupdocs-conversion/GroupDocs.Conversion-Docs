---
id: convert-igs-to-ppt
url: conversion/net/convert-igs-to-ppt
title: Convert IGS to PPT
description: "IGS format represents Initial Graphics Exchange Specification (IGES) with .igs extension. Learn how to convert IGS to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IGS to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .igs (Initial Graphics Exchange) extension is a 2D-3D design exchange file format that is independent of source or destination file format specifications used by CAD applications. It is used to exchange design information about circuit diagrams, wireframes, the freeform surfaces between two independent systems. IGS files can be opened by applications such as Autodesk, FreeCAD, CADEX CAD Exchanger, and other similar applications.

## Steps to convert IGS to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IGS file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IGS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IGS file
using (var converter = new GroupDocs.Conversion.Converter("sample.igs"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### IGS to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**IGS to PPT converter**](https://products.groupdocs.app/conversion/igs-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IGS to PPT"](conversion/net/images/convert-to-ppt/convert-igs-to-ppt.png)](https://products.groupdocs.app/conversion/igs-to-ppt)