---
id: odt-to-ppt
url: conversion/net/convert/odt-to-ppt
title: Convert ODT to PPT
description: "ODT format represents Open Document Text with .odt extension. Learn how to convert ODT to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODT to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google's web-based word processor included with Google Drive can open the ODT files for editing.

## Steps to convert ODT to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODT file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODT file
using (var converter = new GroupDocs.Conversion.Converter("sample.odt"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODT to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**ODT to PPT converter**](https://products.groupdocs.app/conversion/odt-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODT to PPT"](conversion/net/images/convert-to-ppt/convert-odt-to-ppt.png)](https://products.groupdocs.app/conversion/odt-to-ppt)