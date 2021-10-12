---
id: ppt-to-docx
url: conversion/net/convert/ppt-to-docx
title: Convert PPT to DOCX
description: "PPT format represents PowerPoint Presentation with .ppt extension. Learn how to convert PPT to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPT to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with PPT extension represents PowerPoint file that consists of a collection of slides for displaying as SlideShow. It specifies the Binary File Format used by Microsoft PowerPoint 97-2003. A PPT file can contain several different types of information such as text, bulleted points, images, multimedia and other embedded OLE objects. Microsoft came up with newer file format for PowerPoint, known as PPTX, from 2007 onwards that is based on Office OpenXML and is different from this binary file format.

## Steps to convert PPT to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPT file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppt"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPT to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**PPT to DOCX converter**](https://products.groupdocs.app/conversion/ppt-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPT to DOCX"](conversion/net/images/convert-to-docx/convert-ppt-to-docx.png)](https://products.groupdocs.app/conversion/ppt-to-docx)