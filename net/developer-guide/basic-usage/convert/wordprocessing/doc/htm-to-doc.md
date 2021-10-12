---
id: htm-to-doc
url: conversion/net/convert/htm-to-doc
title: Convert HTM to DOC
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for DOC format
   var options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to DOC converter**](https://products.groupdocs.app/conversion/htm-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to DOC"](conversion/net/images/convert-to-doc/convert-htm-to-doc.png)](https://products.groupdocs.app/conversion/htm-to-doc)