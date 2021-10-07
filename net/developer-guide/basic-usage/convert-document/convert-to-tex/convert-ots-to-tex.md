---
id: convert-ots-to-tex
url: conversion/net/convert-ots-to-tex
title: Convert OTS to TEX
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

## Steps to convert OTS to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTS file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ots"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTS to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to TEX converter**](https://products.groupdocs.app/conversion/ots-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to TEX"](conversion/net/images/convert-to-tex/convert-ots-to-tex.png)](https://products.groupdocs.app/conversion/ots-to-tex)