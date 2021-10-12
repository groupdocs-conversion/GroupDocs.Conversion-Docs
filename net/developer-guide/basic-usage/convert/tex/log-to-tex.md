---
id: log-to-tex
url: conversion/net/convert/log-to-tex
title: Convert LOG to TEX
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to TEX converter**](https://products.groupdocs.app/conversion/log-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to TEX"](conversion/net/images/convert-to-tex/convert-log-to-tex.png)](https://products.groupdocs.app/conversion/log-to-tex)