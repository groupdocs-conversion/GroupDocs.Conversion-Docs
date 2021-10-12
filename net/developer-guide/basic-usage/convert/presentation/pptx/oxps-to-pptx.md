---
id: oxps-to-pptx
url: conversion/net/convert/oxps-to-pptx
title: Convert OXPS to PPTX
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

## Steps to convert OXPS to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OXPS file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OXPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OXPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.oxps"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OXPS to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to PPTX converter**](https://products.groupdocs.app/conversion/oxps-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to PPTX"](conversion/net/images/convert-to-pptx/convert-oxps-to-pptx.png)](https://products.groupdocs.app/conversion/oxps-to-pptx)