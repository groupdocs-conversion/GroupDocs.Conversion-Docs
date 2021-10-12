---
id: djvu-to-pptx
url: conversion/net/convert/djvu-to-pptx
title: Convert DJVU to PPTX
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (var converter = new GroupDocs.Conversion.Converter("sample.djvu"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DJVU to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to PPTX converter**](https://products.groupdocs.app/conversion/djvu-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to PPTX"](conversion/net/images/convert-to-pptx/convert-djvu-to-pptx.png)](https://products.groupdocs.app/conversion/djvu-to-pptx)