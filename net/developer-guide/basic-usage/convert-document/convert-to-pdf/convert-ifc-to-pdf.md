---
id: convert-ifc-to-pdf
url: conversion/net/convert-ifc-to-pdf
title: Convert IFC to PDF
description: "IFC format represents Industry Foundation Classes (IFC) File Format with .ifc extension. Learn how to convert IFC to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IFC to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with IFC extension refer to  Industry Foundation Classes (IFC) file format that establishes international standards to import and export building objects and their properties. This file format provides interoperability between different software applications. Specifications for this file format are developed and maintained by buildingSMART International as its Data Standard.

To convert from Industry Foundation Classes (IFC) File Format (.ifc) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source IFC file
using (Converter converter = new Converter("sample.ifc"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**IFC to PDF converter**](https://products.groupdocs.app/conversion/ifc-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IFC to PDF"](conversion/net/images/convert-ifc-to-pdf.png)](https://products.groupdocs.app/conversion/ifc-to-pdf)