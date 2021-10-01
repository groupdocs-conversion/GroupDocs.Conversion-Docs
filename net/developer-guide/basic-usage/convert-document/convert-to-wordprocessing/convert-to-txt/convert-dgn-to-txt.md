---
id: convert-dgn-to-txt
url: conversion/net/convert-dgn-to-txt
title: Convert DGN to TXT
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (var converter = new GroupDocs.Conversion.Converter("sample.dgn"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DGN to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to TXT converter**](https://products.groupdocs.app/conversion/dgn-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to TXT"](conversion/net/images/convert-to-txt/convert-dgn-to-txt.png)](https://products.groupdocs.app/conversion/dgn-to-txt)