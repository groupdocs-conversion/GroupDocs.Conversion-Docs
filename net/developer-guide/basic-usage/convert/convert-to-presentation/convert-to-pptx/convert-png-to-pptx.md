---
id: convert-png-to-pptx
url: conversion/net/convert-png-to-pptx
title: Convert PNG to PPTX
description: "PNG format represents Portable Network Graphic with .png extension. Learn how to convert PNG to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PNG to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PNG, Portable Network Graphics, refers to a type of raster image file format that use loseless compression. This file format was created as a replacement of Graphics Interchange Format (GIF) and has no copyright limitations. However, PNG file format does not support animations. PNG file format supports loseless image compression that makes it popular among its users. With the passage of time, PNG has evolved as one of the mostly used image file format.

## Steps to convert PNG to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PNG file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PNG to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**PNG to PPTX converter**](https://products.groupdocs.app/conversion/png-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PNG to PPTX"](conversion/net/images/convert-to-pptx/convert-png-to-pptx.png)](https://products.groupdocs.app/conversion/png-to-pptx)