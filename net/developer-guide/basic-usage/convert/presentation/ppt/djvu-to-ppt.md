---
id: djvu-to-ppt
url: conversion/net/convert/djvu-to-ppt
title: Convert DJVU to PPT
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to PPT converter**](https://products.groupdocs.app/conversion/djvu-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to PPT"](conversion/net/images/convert-to-ppt/convert-djvu-to-ppt.png)](https://products.groupdocs.app/conversion/djvu-to-ppt)