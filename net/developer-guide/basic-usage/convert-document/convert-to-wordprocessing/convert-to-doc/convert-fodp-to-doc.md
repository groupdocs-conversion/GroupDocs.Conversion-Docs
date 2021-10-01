---
id: convert-fodp-to-doc
url: conversion/net/convert-fodp-to-doc
title: Convert FODP to DOC
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to DOC converter**](https://products.groupdocs.app/conversion/fodp-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to DOC"](conversion/net/images/convert-to-doc/convert-fodp-to-doc.png)](https://products.groupdocs.app/conversion/fodp-to-doc)