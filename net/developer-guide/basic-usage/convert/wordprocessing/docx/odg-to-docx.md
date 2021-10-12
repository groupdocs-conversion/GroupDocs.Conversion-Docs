---
id: odg-to-docx
url: conversion/net/convert/odg-to-docx
title: Convert ODG to DOCX
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

## Steps to convert ODG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODG file
using (var converter = new GroupDocs.Conversion.Converter("sample.odg"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to DOCX converter**](https://products.groupdocs.app/conversion/odg-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to DOCX"](conversion/net/images/convert-to-docx/convert-odg-to-docx.png)](https://products.groupdocs.app/conversion/odg-to-docx)