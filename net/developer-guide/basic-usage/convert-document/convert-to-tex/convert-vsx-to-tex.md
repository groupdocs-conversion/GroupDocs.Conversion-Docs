---
id: convert-vsx-to-tex
url: conversion/net/convert-vsx-to-tex
title: Convert VSX to TEX
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

## Steps to convert VSX to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSX file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsx"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSX to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to TEX converter**](https://products.groupdocs.app/conversion/vsx-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to TEX"](conversion/net/images/convert-to-tex/convert-vsx-to-tex.png)](https://products.groupdocs.app/conversion/vsx-to-tex)