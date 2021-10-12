---
id: convert-cf2-to-doc
url: conversion/net/convert-cf2-to-doc
title: Convert CF2 to DOC
description: "CF2 format represents Common File Format File with .cf2 extension. Learn how to convert CF2 to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CF2 to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .cf2 extension is a CAD file format that contains 3D package designs or other model data for die-cutting. Most of the CAD/CAM machines can process and cut these files. It was created by the National Space Science Data Center (NSSDC) to provide self-describing data storage and manipulation format that matches the structure of scientific data and applications such as statistical and numerical methods, visualization, and management. 

## Steps to convert CF2 to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CF2 file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CF2 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CF2 file
using (var converter = new GroupDocs.Conversion.Converter("sample.cf2"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CF2 to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**CF2 to DOC converter**](https://products.groupdocs.app/conversion/cf2-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CF2 to DOC"](conversion/net/images/convert-to-doc/convert-cf2-to-doc.png)](https://products.groupdocs.app/conversion/cf2-to-doc)