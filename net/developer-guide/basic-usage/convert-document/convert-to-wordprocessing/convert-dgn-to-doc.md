---
id: convert-dgn-to-doc
url: conversion/net/convert-dgn-to-doc
title: Convert DGN to DOC
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (var converter = new GroupDocs.Conversion.Converter("sample.dgn"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to DOC converter**](https://products.groupdocs.app/conversion/dgn-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to DOC"](conversion/net/images/convert-dgn-to-doc.png)](https://products.groupdocs.app/conversion/dgn-to-doc)