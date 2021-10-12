---
id: mobi-to-doc
url: conversion/net/convert/mobi-to-doc
title: Convert MOBI to DOC
description: "MOBI format represents Mobipocket eBook with .mobi extension. Learn how to convert MOBI to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MOBI to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The MOBI file format is one of the most widely used ebook file formats. The format is an enhancement to the old OEB (Open Ebook Format) format and was used as the proprietary format for Mobipocket Reader. Like EPUB, it is supported by almost all modern e-readers specifically by mobile devices with low bandwidth. The format can be converted to several other formats such as PDF, EPUB, and several other formats using publicly available software applications such as the Kindle app.

## Steps to convert MOBI to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MOBI file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MOBI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MOBI file
using (var converter = new GroupDocs.Conversion.Converter("sample.mobi"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MOBI to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**MOBI to DOC converter**](https://products.groupdocs.app/conversion/mobi-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MOBI to DOC"](conversion/net/images/convert-to-doc/convert-mobi-to-doc.png)](https://products.groupdocs.app/conversion/mobi-to-doc)