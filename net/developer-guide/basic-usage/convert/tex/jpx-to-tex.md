---
id: jpx-to-tex
url: conversion/net/convert/jpx-to-tex
title: Convert JPX to TEX
description: "JPX format represents JPEG 2000 Image File with .jpx extension. Learn how to convert JPX to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPX to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPX is a JPEG 2000 extended file-format. JPEG 2000 is an improvement to the JPEG format.

## Steps to convert JPX to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPX file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpx"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPX to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to TEX converter**](https://products.groupdocs.app/conversion/jpx-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to TEX"](conversion/net/images/convert-to-tex/convert-jpx-to-tex.png)](https://products.groupdocs.app/conversion/jpx-to-tex)