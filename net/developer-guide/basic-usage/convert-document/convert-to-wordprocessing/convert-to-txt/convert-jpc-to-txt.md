---
id: convert-jpc-to-txt
url: conversion/net/convert-jpc-to-txt
title: Convert JPC to TXT
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to TXT converter**](https://products.groupdocs.app/conversion/jpc-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to TXT"](conversion/net/images/convert-to-txt/convert-jpc-to-txt.png)](https://products.groupdocs.app/conversion/jpc-to-txt)