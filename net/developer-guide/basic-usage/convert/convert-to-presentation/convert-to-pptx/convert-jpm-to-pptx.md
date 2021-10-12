---
id: convert-jpm-to-pptx
url: conversion/net/convert-jpm-to-pptx
title: Convert JPM to PPTX
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to PPTX converter**](https://products.groupdocs.app/conversion/jpm-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to PPTX"](conversion/net/images/convert-to-pptx/convert-jpm-to-pptx.png)](https://products.groupdocs.app/conversion/jpm-to-pptx)