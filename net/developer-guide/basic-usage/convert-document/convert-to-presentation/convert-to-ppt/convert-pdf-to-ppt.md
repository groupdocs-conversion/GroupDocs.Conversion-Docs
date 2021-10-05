---
id: convert-pdf-to-ppt
url: conversion/net/convert-pdf-to-ppt
title: Convert PDF to PPT
description: "PDF format represents Portable Document with .pdf extension. Learn how to convert PDF to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PDF to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

## Steps to convert PDF to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PDF file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PDF to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**PDF to PPT converter**](https://products.groupdocs.app/conversion/pdf-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PDF to PPT"](conversion/net/images/convert-to-ppt/convert-pdf-to-ppt.png)](https://products.groupdocs.app/conversion/pdf-to-ppt)