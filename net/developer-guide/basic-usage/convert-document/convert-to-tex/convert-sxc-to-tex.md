---
id: convert-sxc-to-tex
url: conversion/net/convert-sxc-to-tex
title: Convert SXC to TEX
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to TEX converter**](https://products.groupdocs.app/conversion/sxc-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to TEX"](conversion/net/images/convert-to-tex/convert-sxc-to-tex.png)](https://products.groupdocs.app/conversion/sxc-to-tex)