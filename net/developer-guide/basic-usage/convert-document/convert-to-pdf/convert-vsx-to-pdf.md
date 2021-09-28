---
id: convert-vsx-to-pdf
url: conversion/net/convert-vsx-to-pdf
title: Convert VSX to PDF
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

To convert from Vector Scalar Extension (.vsx) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source VSX file
using (Converter converter = new Converter("sample.vsx"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to PDF converter**](https://products.groupdocs.app/conversion/vsx-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to PDF"](conversion/net/images/convert-vsx-to-pdf.png)](https://products.groupdocs.app/conversion/vsx-to-pdf)