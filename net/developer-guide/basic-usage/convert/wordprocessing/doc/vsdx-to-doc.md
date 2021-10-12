---
id: vsdx-to-doc
url: conversion/net/convert/vsdx-to-doc
title: Convert VSDX to DOC
description: "VSDX format represents Microsoft Visio File Format with .vsdx extension. Learn how to convert VSDX to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDX to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

## Steps to convert VSDX to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDX file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsdx"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDX to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to DOC converter**](https://products.groupdocs.app/conversion/vsdx-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to DOC"](conversion/net/images/convert-to-doc/convert-vsdx-to-doc.png)](https://products.groupdocs.app/conversion/vsdx-to-doc)