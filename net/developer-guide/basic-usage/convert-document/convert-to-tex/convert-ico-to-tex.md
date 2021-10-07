---
id: convert-ico-to-tex
url: conversion/net/convert-ico-to-tex
title: Convert ICO to TEX
description: "ICO format represents Microsoft Icon File with .ico extension. Learn how to convert ICO to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ICO to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ICO extension are image file types used as icon for representation of an application on Microsoft Windows. These come in different size, colour support and resolution to suit the requirements of the display. Another similar image file format on Microsoft Windows is .CUR for cursor representation and defines a hotspot in the image header. On MacOS, ICNS file formats serve the same purpose as ICO files. Several online websites as well as applications provide the feature of creating such files and convert other image formats such as BMP, PNG, etc. to icon file format. The official IANA registered Internet media type for ICO files is image/vnd.microsoft.icon.

## Steps to convert ICO to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ICO file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ICO file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ICO file
using (var converter = new GroupDocs.Conversion.Converter("sample.ico"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ICO to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**ICO to TEX converter**](https://products.groupdocs.app/conversion/ico-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ICO to TEX"](conversion/net/images/convert-to-tex/convert-ico-to-tex.png)](https://products.groupdocs.app/conversion/ico-to-tex)