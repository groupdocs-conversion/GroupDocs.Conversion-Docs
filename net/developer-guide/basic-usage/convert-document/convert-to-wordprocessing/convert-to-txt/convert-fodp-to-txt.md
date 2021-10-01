---
id: convert-fodp-to-txt
url: conversion/net/convert-fodp-to-txt
title: Convert FODP to TXT
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to TXT converter**](https://products.groupdocs.app/conversion/fodp-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to TXT"](conversion/net/images/convert-to-txt/convert-fodp-to-txt.png)](https://products.groupdocs.app/conversion/fodp-to-txt)