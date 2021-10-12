---
id: xltx-to-pptx
url: conversion/net/convert/xltx-to-pptx
title: Convert XLTX to PPTX
description: "XLTX format represents Microsoft Excel Open XML Template with .xltx extension. Learn how to convert XLTX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLTX to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLTX extension represent Microsoft Excel Template files that are based on the Office OpenXML file format specifications. It is used to create a standard template file that can be utilized to generate XLSX files that exhibit the same settings as specified in the XLTX file.

## Steps to convert XLTX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLTX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xltx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLTX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**XLTX to PPTX converter**](https://products.groupdocs.app/conversion/xltx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLTX to PPTX"](conversion/net/images/convert-to-pptx/convert-xltx-to-pptx.png)](https://products.groupdocs.app/conversion/xltx-to-pptx)