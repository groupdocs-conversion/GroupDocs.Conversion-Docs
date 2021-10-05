---
id: convert-fodp-to-pptx
url: conversion/net/convert-fodp-to-pptx
title: Convert FODP to PPTX
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to PPTX converter**](https://products.groupdocs.app/conversion/fodp-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to PPTX"](conversion/net/images/convert-to-pptx/convert-fodp-to-pptx.png)](https://products.groupdocs.app/conversion/fodp-to-pptx)