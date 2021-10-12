---
id: md-to-tex
url: conversion/net/convert/md-to-tex
title: Convert MD to TEX
description: "MD format represents Markdown with .md extension. Learn how to convert MD to TEX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to TEX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

## Steps to convert MD to TEX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MD file to TEX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PdfFileType.Tex`.
* Call `Converter` class `Convert` method and pass the filename for the converted TEX file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MD file
using (var converter = new GroupDocs.Conversion.Converter("sample.md"))
{
    // Set the convert options for TEX format
   var options = new PdfConvertOptions { Format = GroupDocs.Conversion.FileTypes.PdfFileType.Tex };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MD to TEX Live Demo

GroupDocs.Conversion for .NET provides an online [**MD to TEX converter**](https://products.groupdocs.app/conversion/md-to-tex), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to TEX"](conversion/net/images/convert-to-tex/convert-md-to-tex.png)](https://products.groupdocs.app/conversion/md-to-tex)