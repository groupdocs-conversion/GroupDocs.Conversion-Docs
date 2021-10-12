---
id: vdw-to-pptx
url: conversion/net/convert/vdw-to-pptx
title: Convert VDW to PPTX
description: "VDW format represents Visio Web Drawing with .vdw extension. Learn how to convert VDW to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDW to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VDW is the Visio Graphics Service file format that specifies the streams and storages required for rendering a Web drawing. A web drawing is a collection of drawing pages, shapes, fonts, images, data connections, and diagram update information that can be rendered as a vector or raster drawing. VDW files can be opened in Microsoft Visio as well but are primarily saved for use on the web.

## Steps to convert VDW to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDW file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDW file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDW file
using (var converter = new GroupDocs.Conversion.Converter("sample.vdw"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VDW to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**VDW to PPTX converter**](https://products.groupdocs.app/conversion/vdw-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDW to PPTX"](conversion/net/images/convert-to-pptx/convert-vdw-to-pptx.png)](https://products.groupdocs.app/conversion/vdw-to-pptx)