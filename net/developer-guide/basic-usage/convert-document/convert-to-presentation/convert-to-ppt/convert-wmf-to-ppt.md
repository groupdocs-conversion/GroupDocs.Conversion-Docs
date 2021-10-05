---
id: convert-wmf-to-ppt
url: conversion/net/convert-wmf-to-ppt
title: Convert WMF to PPT
description: "WMF format represents Windows Metafile with .wmf extension. Learn how to convert WMF to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert WMF to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with WMF extension represent Microsoft Windows Metafile (WMF) for storing vector as well as bitmap-format images data. To be more accurate, WMF belongs to the vector file format category of Graphics file formats that is device independent. Windows Graphical Device Interface (GDI) uses the functions stored in a WMF file to display an image on the screen.

## Steps to convert WMF to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the WMF file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source WMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source WMF file
using (var converter = new GroupDocs.Conversion.Converter("sample.wmf"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### WMF to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**WMF to PPT converter**](https://products.groupdocs.app/conversion/wmf-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert WMF to PPT"](conversion/net/images/convert-to-ppt/convert-wmf-to-ppt.png)](https://products.groupdocs.app/conversion/wmf-to-ppt)