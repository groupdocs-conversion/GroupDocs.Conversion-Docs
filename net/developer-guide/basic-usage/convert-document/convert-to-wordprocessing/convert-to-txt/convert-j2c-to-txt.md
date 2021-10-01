---
id: convert-j2c-to-txt
url: conversion/net/convert-j2c-to-txt
title: Convert J2C to TXT
description: "J2C format represents JPEG 2000 Image File with .j2c extension. Learn how to convert J2C to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert J2C to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A J2C file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert J2C to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the J2C file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source J2C file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source J2C file
using (var converter = new GroupDocs.Conversion.Converter("sample.j2c"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### J2C to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**J2C to TXT converter**](https://products.groupdocs.app/conversion/j2c-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert J2C to TXT"](conversion/net/images/convert-to-txt/convert-j2c-to-txt.png)](https://products.groupdocs.app/conversion/j2c-to-txt)