---
id: vsx-to-pptx
url: conversion/net/convert/vsx-to-pptx
title: Convert VSX to PPTX
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

## Steps to convert VSX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to PPTX converter**](https://products.groupdocs.app/conversion/vsx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to PPTX"](conversion/net/images/convert-to-pptx/convert-vsx-to-pptx.png)](https://products.groupdocs.app/conversion/vsx-to-pptx)