---
id: dwf-to-tex
url: conversion/net/convert/dwf-to-tex
title: Convert DWF to TEX
description: "DWF format represents Design Web Format with .dwf extension. Learn how to convert DWF to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWF to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Design Web Format (DWF) represents 2D/3D drawing in compressed format for viewing, reviewing, or printing design files. It contains graphics and text as part of design data and reduces the size of the file due to its compressed format. The reduced file size makes the distribution and communication of rich design data efficient. DWF doesn't require the recipient to know about the usage of CAD software that created the original drawing.

## Steps to convert DWF to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWF file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwf"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWF to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWF to TEX converter**](https://products.groupdocs.app/conversion/dwf-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWF to TEX"](conversion/net/images/convert-to-tex/convert-dwf-to-tex.png)](https://products.groupdocs.app/conversion/dwf-to-tex)