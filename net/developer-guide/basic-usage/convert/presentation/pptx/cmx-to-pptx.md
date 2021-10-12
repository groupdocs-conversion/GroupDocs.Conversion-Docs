---
id: cmx-to-pptx
url: conversion/net/convert/cmx-to-pptx
title: Convert CMX to PPTX
description: "CMX format represents Corel Metafile Exchange Image File with .cmx extension. Learn how to convert CMX to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CMX to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with CMX extension are Corel Exchange image file format (also known as Corel Metafile Exchange) that is used as presentation by CorelSuite applications. It contains image data as vector graphics as well as metadata that describes the image. CMX files can be opened by CorelDraw, Corel Presentations, Paint Shop Pro and some versions of Adobe Illustrator. CMX files can be converted to other formats such as JPG and EPS.

## Steps to convert CMX to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CMX file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CMX file
using (var converter = new GroupDocs.Conversion.Converter("sample.cmx"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CMX to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**CMX to PPTX converter**](https://products.groupdocs.app/conversion/cmx-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CMX to PPTX"](conversion/net/images/convert-to-pptx/convert-cmx-to-pptx.png)](https://products.groupdocs.app/conversion/cmx-to-pptx)