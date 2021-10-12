---
id: dgn-to-tex
url: conversion/net/convert/dgn-to-tex
title: Convert DGN to TEX
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (var converter = new GroupDocs.Conversion.Converter("sample.dgn"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DGN to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to TEX converter**](https://products.groupdocs.app/conversion/dgn-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to TEX"](conversion/net/images/convert-to-tex/convert-dgn-to-tex.png)](https://products.groupdocs.app/conversion/dgn-to-tex)