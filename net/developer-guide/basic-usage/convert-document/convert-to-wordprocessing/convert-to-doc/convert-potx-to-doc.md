---
id: convert-potx-to-doc
url: conversion/net/convert-potx-to-doc
title: Convert POTX to DOC
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

## Steps to convert POTX to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTX file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.potx"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTX to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to DOC converter**](https://products.groupdocs.app/conversion/potx-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to DOC"](conversion/net/images/convert-to-doc/convert-potx-to-doc.png)](https://products.groupdocs.app/conversion/potx-to-doc)