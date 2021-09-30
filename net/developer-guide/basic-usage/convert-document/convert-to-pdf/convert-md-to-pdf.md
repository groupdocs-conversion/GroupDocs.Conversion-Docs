---
id: convert-md-to-pdf
url: conversion/net/convert-md-to-pdf
title: Convert MD to PDF
description: "MD format represents Markdown with .md extension. Learn how to convert MD to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

## Steps to convert MD to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MD file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MD file
using (var converter = new GroupDocs.Conversion.Converter("sample.md"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MD to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**MD to PDF converter**](https://products.groupdocs.app/conversion/md-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to PDF"](conversion/net/images/convert-to-pdf/convert-md-to-pdf.png)](https://products.groupdocs.app/conversion/md-to-pdf)