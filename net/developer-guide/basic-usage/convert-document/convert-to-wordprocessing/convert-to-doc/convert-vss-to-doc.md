---
id: convert-vss-to-doc
url: conversion/net/convert-vss-to-doc
title: Convert VSS to DOC
description: "VSS format represents Visio Stencil File with .vss extension. Learn how to convert VSS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSS to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSS is stencil files created with Microsoft Visio 2007 and earlier. A relatively new file format is VSSX that was introduced with Microsoft Visio 2013. Stencil files provide drawing objects that can be included in a VSD Visio drawing. Microsoft Visio is used for creating drawing elements such as a collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping, and other similar information.

## Steps to convert VSS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSS file
using (var converter = new GroupDocs.Conversion.Converter("sample.vss"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**VSS to DOC converter**](https://products.groupdocs.app/conversion/vss-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSS to DOC"](conversion/net/images/convert-to-doc/convert-vss-to-doc.png)](https://products.groupdocs.app/conversion/vss-to-doc)