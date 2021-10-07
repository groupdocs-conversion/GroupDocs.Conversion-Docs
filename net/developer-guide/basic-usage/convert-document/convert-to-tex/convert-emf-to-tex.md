---
id: convert-emf-to-tex
url: conversion/net/convert-emf-to-tex
title: Convert EMF to TEX
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

## Steps to convert EMF to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMF file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMF file
using (var converter = new GroupDocs.Conversion.Converter("sample.emf"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMF to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to TEX converter**](https://products.groupdocs.app/conversion/emf-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to TEX"](conversion/net/images/convert-to-tex/convert-emf-to-tex.png)](https://products.groupdocs.app/conversion/emf-to-tex)