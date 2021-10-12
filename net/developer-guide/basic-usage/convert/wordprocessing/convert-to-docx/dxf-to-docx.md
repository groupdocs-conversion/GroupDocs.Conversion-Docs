---
id: dxf-to-docx
url: conversion/net/convert/dxf-to-docx
title: Convert DXF to DOCX
description: "DXF format represents Autodesk Drawing Exchange File Format with .dxf extension. Learn how to convert DXF to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DXF to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DXF, Drawing Interchange Format, or Drawing Exchange Format, is a tagged data representation of AutoCAD drawing file. Each element in the file has a prefix integer number called a group code. This group code actually represents the element that follows and indicates the meaning of a data element for a given object type. DXF makes it possible to represent almost all user-specified information in a drawing file.

## Steps to convert DXF to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DXF file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DXF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DXF file
using (var converter = new GroupDocs.Conversion.Converter("sample.dxf"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DXF to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DXF to DOCX converter**](https://products.groupdocs.app/conversion/dxf-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DXF to DOCX"](conversion/net/images/convert-to-docx/convert-dxf-to-docx.png)](https://products.groupdocs.app/conversion/dxf-to-docx)