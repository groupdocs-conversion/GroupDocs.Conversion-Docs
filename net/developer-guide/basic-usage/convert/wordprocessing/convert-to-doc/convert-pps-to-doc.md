---
id: convert-pps-to-doc
url: conversion/net/convert-pps-to-doc
title: Convert PPS to DOC
description: "PPS format represents Microsoft PowerPoint Slide Show with .pps extension. Learn how to convert PPS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPS to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PPS, PowerPoint Slide Show, files are created using Microsoft PowerPoint for Slide Show purpose. PPS file reading and creation is supported by Microsoft PowerPoint 97-2003. The more latest version of this file format is PPSX which is based on Office OpenXML standards. PPS files can still be read by latest versions of Microsoft PowerPoint, but newly created files can only be saved in PPSX file format. When a PPS file is shared with another user and opened, it starts as Powerpoint show unlike PPT file which opens in editable mode. 

## Steps to convert PPS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.pps"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**PPS to DOC converter**](https://products.groupdocs.app/conversion/pps-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPS to DOC"](conversion/net/images/convert-to-doc/convert-pps-to-doc.png)](https://products.groupdocs.app/conversion/pps-to-doc)