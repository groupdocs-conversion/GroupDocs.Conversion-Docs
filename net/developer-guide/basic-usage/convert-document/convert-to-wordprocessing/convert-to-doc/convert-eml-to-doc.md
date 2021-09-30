---
id: convert-eml-to-doc
url: conversion/net/convert-eml-to-doc
title: Convert EML to DOC
description: "EML format represents E-Mail Message File with .eml extension. Learn how to convert EML to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EML to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EML file format represents email messages saved using Outlook and other relevant applications. Almost all emailing clients support this file format for its compliance with RFC-822 Internet Message Format Standard. Microsoft Outlook is default software for opening EML message types. EML files can be used for saving to disc as well as sending out to recipients using communication protocols.

## Steps to convert EML to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EML file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source EML file
using (var converter = new GroupDocs.Conversion.Converter("sample.eml"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EML to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**EML to DOC converter**](https://products.groupdocs.app/conversion/eml-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EML to DOC"](conversion/net/images/convert-to-doc/convert-eml-to-doc.png)](https://products.groupdocs.app/conversion/eml-to-doc)