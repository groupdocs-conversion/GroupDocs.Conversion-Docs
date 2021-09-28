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

## Steps to convert POT to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POT file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POT file
using (var converter = new GroupDocs.Conversion.Converter("sample.pot"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**POT to PDF converter**](https://products.groupdocs.app/conversion/pot-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POT to PDF"](conversion/net/images/convert-pot-to-pdf.png)](https://products.groupdocs.app/conversion/pot-to-pdf)