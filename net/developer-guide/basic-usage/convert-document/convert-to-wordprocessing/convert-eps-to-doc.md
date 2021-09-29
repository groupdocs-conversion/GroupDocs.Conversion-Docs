---
id: convert-eps-to-doc
url: conversion/net/convert-eps-to-doc
title: Convert EPS to DOC
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to DOC converter**](https://products.groupdocs.app/conversion/eps-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to DOC"](conversion/net/images/convert-eps-to-doc.png)](https://products.groupdocs.app/conversion/eps-to-doc)