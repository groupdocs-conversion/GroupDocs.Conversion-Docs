---
id: convert-emz-to-tex
url: conversion/net/convert-emz-to-tex
title: Convert EMZ to TEX
description: "EMZ format represents Enhanced Windows Metafile Compressed with .emz extension. Learn how to convert EMZ to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMZ to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .emz extension is a compressed container of Enhanced Metafile (.emf file). It follows GZIP compression algorithm and takes less storage space due to compression. The small file size makes it more easy to transfer EMZ files over the network.

## Steps to convert EMZ to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMZ file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMZ file
using (var converter = new GroupDocs.Conversion.Converter("sample.emz"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMZ to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to TEX converter**](https://products.groupdocs.app/conversion/emz-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to TEX"](conversion/net/images/convert-to-tex/convert-emz-to-tex.png)](https://products.groupdocs.app/conversion/emz-to-tex)