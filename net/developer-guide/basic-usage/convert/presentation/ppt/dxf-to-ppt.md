---
id: dxf-to-ppt
url: conversion/net/convert/dxf-to-ppt
title: Convert DXF to PPT
description: "DXF format represents Autodesk Drawing Exchange File Format with .dxf extension. Learn how to convert DXF to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DXF to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DXF, Drawing Interchange Format, or Drawing Exchange Format, is a tagged data representation of AutoCAD drawing file. Each element in the file has a prefix integer number called a group code. This group code actually represents the element that follows and indicates the meaning of a data element for a given object type. DXF makes it possible to represent almost all user-specified information in a drawing file.

## Steps to convert DXF to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DXF file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DXF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DXF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dxf"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DXF to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**DXF to PPT converter**](https://products.groupdocs.app/conversion/dxf-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DXF to PPT"](conversion/net/images/convert-to-ppt/convert-dxf-to-ppt.png)](https://products.groupdocs.app/conversion/dxf-to-ppt)