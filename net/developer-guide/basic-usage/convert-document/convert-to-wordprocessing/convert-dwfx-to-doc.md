---
id: convert-dwfx-to-doc
url: conversion/net/convert-dwfx-to-doc
title: Convert DWFX to DOC
description: "DWFX format represents Design Web Format XPS with .dwfx extension. Learn how to convert DWFX to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWFX to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWFx (Design Web Format XPS) is a a formatted representation of 2D/3D drawing as XPS document. It contains graphics and text as part of design data. It is the newest version of DWF file format and can be viewed and printed with the Microsoft XPS Viewer. The XPS nature of these files lets you share the design data with reviewers without requiring them to install Autodesk Design Review. Similar to DWF, DWFx is developed by Autodesk in compressed format to make transmission over the internet suitable. A single DWFx file can contain one or multiple drawings and sheet sets.

## Steps to convert DWFX to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWFX file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWFX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWFX file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwfx"))
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

GroupDocs.Conversion for .NET provides an online [**DWFX to DOC converter**](https://products.groupdocs.app/conversion/dwfx-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWFX to DOC"](conversion/net/images/convert-dwfx-to-doc.png)](https://products.groupdocs.app/conversion/dwfx-to-doc)