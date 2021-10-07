---
id: convert-fodp-to-tex
url: conversion/net/convert-fodp-to-tex
title: Convert FODP to TEX
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to TEX converter**](https://products.groupdocs.app/conversion/fodp-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to TEX"](conversion/net/images/convert-to-tex/convert-fodp-to-tex.png)](https://products.groupdocs.app/conversion/fodp-to-tex)