---
id: convert-pot-to-doc
url: conversion/net/convert-pot-to-doc
title: Convert POT to DOC
description: "POT format represents PowerPoint Template with .pot extension. Learn how to convert POT to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POT to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POT extension represent Microsoft PowerPoint template files created by PowerPoint 97-2003 versions. Files created with these versions of Microsoft PowerPoint are in binary format as compared to those created in Office OpenXML file formats using the higher versions of PowerPoint. The files, hence, generated can be used to create presentations that have the same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, color palettes, fonts, and defaults.

## Steps to convert POT to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POT file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POT file
using (var converter = new GroupDocs.Conversion.Converter("sample.pot"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POT to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**POT to DOC converter**](https://products.groupdocs.app/conversion/pot-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POT to DOC"](conversion/net/images/convert-pot-to-doc.png)](https://products.groupdocs.app/conversion/pot-to-doc)