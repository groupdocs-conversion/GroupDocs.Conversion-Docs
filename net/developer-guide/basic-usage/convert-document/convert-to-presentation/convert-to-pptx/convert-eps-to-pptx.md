---
id: convert-eps-to-pptx
url: conversion/net/convert-eps-to-pptx
title: Convert EPS to PPTX
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to PPTX converter**](https://products.groupdocs.app/conversion/eps-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to PPTX"](conversion/net/images/convert-to-pptx/convert-eps-to-pptx.png)](https://products.groupdocs.app/conversion/eps-to-pptx)