---
id: convert-dxf-to-doc
url: conversion/net/convert-dxf-to-doc
title: Convert DXF to DOC
description: "DXF format represents Autodesk Drawing Exchange File Format with .dxf extension. Learn how to convert DXF to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DXF to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DXF, Drawing Interchange Format, or Drawing Exchange Format, is a tagged data representation of AutoCAD drawing file. Each element in the file has a prefix integer number called a group code. This group code actually represents the element that follows and indicates the meaning of a data element for a given object type. DXF makes it possible to represent almost all user-specified information in a drawing file.

## Steps to convert DXF to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DXF file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DXF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DXF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dxf"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DXF to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**DXF to DOC converter**](https://products.groupdocs.app/conversion/dxf-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DXF to DOC"](conversion/net/images/convert-to-doc/convert-dxf-to-doc.png)](https://products.groupdocs.app/conversion/dxf-to-doc)