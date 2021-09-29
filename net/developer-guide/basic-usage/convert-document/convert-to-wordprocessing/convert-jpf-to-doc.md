---
id: convert-jpf-to-doc
url: conversion/net/convert-jpf-to-doc
title: Convert JPF to DOC
description: "JPF format represents JPEG 2000 Image File with .jpf extension. Learn how to convert JPF to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPF to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPEG 2000 is an image coding system and state-of-the-art image compression standard. It uses wavelet technology to code lossless content in any quality at once. Moreover, without any substantial penalty in coding efficiency, JPEG 2000 has the capability to access and decode the same content efficaciously into a variety of other resolutions and qualities. The code streams in JPEG 2000 are significantly scalable having regions of interest that provide the facility for spatial random access.

## Steps to convert JPF to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPF file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPF file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpf"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**JPF to DOC converter**](https://products.groupdocs.app/conversion/jpf-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPF to DOC"](conversion/net/images/convert-jpf-to-doc.png)](https://products.groupdocs.app/conversion/jpf-to-doc)