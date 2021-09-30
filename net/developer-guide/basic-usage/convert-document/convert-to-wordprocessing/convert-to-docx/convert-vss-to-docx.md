---
id: convert-vss-to-docx
url: conversion/net/convert-vss-to-docx
title: Convert VSS to DOCX
description: "VSS format represents Visio Stencil File with .vss extension. Learn how to convert VSS to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSS to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VSS is stencil files created with Microsoft Visio 2007 and earlier. A relatively new file format is VSSX that was introduced with Microsoft Visio 2013. Stencil files provide drawing objects that can be included in a VSD Visio drawing. Microsoft Visio is used for creating drawing elements such as a collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping, and other similar information.

## Steps to convert VSS to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSS file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSS file
using (var converter = new GroupDocs.Conversion.Converter("sample.vss"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSS to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**VSS to DOCX converter**](https://products.groupdocs.app/conversion/vss-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSS to DOCX"](conversion/net/images/convert-to-docx/convert-vss-to-docx.png)](https://products.groupdocs.app/conversion/vss-to-docx)