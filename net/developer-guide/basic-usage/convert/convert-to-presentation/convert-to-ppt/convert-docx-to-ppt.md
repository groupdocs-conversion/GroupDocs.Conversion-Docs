---
id: convert-docx-to-ppt
url: conversion/net/convert-docx-to-ppt
title: Convert DOCX to PPT
description: "DOCX format represents Microsoft Word Open XML Document with .docx extension. Learn how to convert DOCX to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCX to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

## Steps to convert DOCX to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCX file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOCX to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCX to PPT converter**](https://products.groupdocs.app/conversion/docx-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCX to PPT"](conversion/net/images/convert-to-ppt/convert-docx-to-ppt.png)](https://products.groupdocs.app/conversion/docx-to-ppt)