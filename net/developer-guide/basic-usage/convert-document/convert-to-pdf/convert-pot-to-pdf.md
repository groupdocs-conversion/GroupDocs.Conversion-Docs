---
id: convert-pot-to-pdf
url: conversion/net/convert-pot-to-pdf
title: Convert POT to PDF
description: "POT format represents PowerPoint Template with .pot extension. Learn how to convert POT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POT extension represent Microsoft PowerPoint template files created by PowerPoint 97-2003 versions. Files created with these versions of Microsoft PowerPoint are in binary format as compared to those created in Office OpenXML file formats using the higher versions of PowerPoint. The files, hence, generated can be used to create presentations that have the same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, color palettes, fonts, and defaults.

To convert from PowerPoint Template (.pot) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source POT file
using (Converter converter = new Converter("sample.pot"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**POT to PDF converter**](https://products.groupdocs.app/conversion/pot-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POT to PDF"](conversion/net/images/convert-pot-to-pdf.png)](https://products.groupdocs.app/conversion/pot-to-pdf)