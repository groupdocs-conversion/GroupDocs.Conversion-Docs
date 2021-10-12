---
id: convert-docx-to-png
url: conversion/net/convert-docx-to-png
title: Convert DOCX to PNG
description: "DOCX format represents Microsoft Word Open XML Document with .docx extension. Learn how to convert DOCX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

## Steps to convert DOCX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DOCX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCX file
using (Converter converter = new Converter("sample.docx"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOCX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCX to PNG converter**](https://products.groupdocs.app/conversion/docx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCX to PNG"](conversion/net/images/convert-to-png/convert-docx-to-png.png)](https://products.groupdocs.app/conversion/docx-to-png)