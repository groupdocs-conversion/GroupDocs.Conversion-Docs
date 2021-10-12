---
id: ppsm-to-tex
url: conversion/net/convert/ppsm-to-tex
title: Convert PPSM to TEX
description: "PPSM format represents Microsoft PowerPoint Slide Show with .ppsm extension. Learn how to convert PPSM to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSM to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is PPTM which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as slide show, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening it in PowerPoint.

## Steps to convert PPSM to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPSM file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppsm"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPSM to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSM to TEX converter**](https://products.groupdocs.app/conversion/ppsm-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSM to TEX"](conversion/net/images/convert-to-tex/convert-ppsm-to-tex.png)](https://products.groupdocs.app/conversion/ppsm-to-tex)