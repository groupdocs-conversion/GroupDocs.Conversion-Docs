---
id: cgm-to-pptx
url: conversion/net/convert/cgm-to-pptx
title: Convert CGM to PPTX
description: "CGM format represents Computer Graphics Metafile with .cgm extension. Learn how to convert CGM to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CGM to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Computer Graphics Metafile (CGM) is free, platform-independent, international standard metafile format for storing and exchanging vector graphics (2D), raster graphics, and text. CGM uses an object-oriented approach and many function provisions for image production. CGM uses these object-oriented characteristics for remolding graphical elements to render an image. A metafile contains necessary information that defines other files. In CGM, a text-based source file contains all graphical elements that can be later compiled into a binary file.

## Steps to convert CGM to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CGM file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CGM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CGM file
using (var converter = new GroupDocs.Conversion.Converter("sample.cgm"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CGM to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**CGM to PPTX converter**](https://products.groupdocs.app/conversion/cgm-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CGM to PPTX"](conversion/net/images/convert-to-pptx/convert-cgm-to-pptx.png)](https://products.groupdocs.app/conversion/cgm-to-pptx)