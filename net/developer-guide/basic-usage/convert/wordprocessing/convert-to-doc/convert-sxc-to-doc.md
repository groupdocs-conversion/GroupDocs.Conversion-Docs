---
id: convert-sxc-to-doc
url: conversion/net/convert-sxc-to-doc
title: Convert SXC to DOC
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to DOC converter**](https://products.groupdocs.app/conversion/sxc-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to DOC"](conversion/net/images/convert-to-doc/convert-sxc-to-doc.png)](https://products.groupdocs.app/conversion/sxc-to-doc)