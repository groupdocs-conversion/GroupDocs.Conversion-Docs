---
id: convert-svg-to-doc
url: conversion/net/convert-svg-to-doc
title: Convert SVG to DOC
description: "SVG format represents Scalable Vector Graphics File with .svg extension. Learn how to convert SVG to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVG to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

SVG files are Scalable Vector Graphics Files that use XML based text format for describing the appearance of image. The word Scalable refers to the fact that the SVG can be scaled to different sizes without losing any quality. Text based description of such files make them independent of resolution. It is one of the mostly used format for building website and print graphics in order to achieve scalability.

## Steps to convert SVG to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVG file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source SVG file
using (var converter = new GroupDocs.Conversion.Converter("sample.svg"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVG to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**SVG to DOC converter**](https://products.groupdocs.app/conversion/svg-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVG to DOC"](conversion/net/images/convert-to-doc/convert-svg-to-doc.png)](https://products.groupdocs.app/conversion/svg-to-doc)