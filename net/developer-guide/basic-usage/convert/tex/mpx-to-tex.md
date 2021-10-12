---
id: mpx-to-tex
url: conversion/net/convert/mpx-to-tex
title: Convert MPX to TEX
description: "MPX format represents Microsoft Project Exchange File with .mpx extension. Learn how to convert MPX to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPX to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MPX, Microsoft Exchange File Format, is an ASCII file format for transferring project information between Microsoft Project (MSP) and other applications that support the MPX file format such as Primavera Project Planner, Sciforma, and Timberline Precision Estimating. The MPX file format allows you to transfer project information that cannot appear in a table, such as detailed resource assignment information, calendar information, or information in the Project Info dialog box.

## Steps to convert MPX to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPX file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpx"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPX to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**MPX to TEX converter**](https://products.groupdocs.app/conversion/mpx-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPX to TEX"](conversion/net/images/convert-to-tex/convert-mpx-to-tex.png)](https://products.groupdocs.app/conversion/mpx-to-tex)