---
id: convert-potx-to-pdf
url: conversion/net/convert-potx-to-pdf
title: Convert POTX to PDF
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

To convert from Microsoft PowerPoint Open XML Template (.potx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source POTX file
using (Converter converter = new Converter("sample.potx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to PDF converter**](https://products.groupdocs.app/conversion/potx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to PDF"](conversion/net/images/convert-potx-to-pdf.png)](https://products.groupdocs.app/conversion/potx-to-pdf)