---
id: convert-htm-to-pdf
url: conversion/net/convert-htm-to-pdf
title: Convert HTM to PDF
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PDF converter**](https://products.groupdocs.app/conversion/htm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PDF"](conversion/net/images/convert-htm-to-pdf.png)](https://products.groupdocs.app/conversion/htm-to-pdf)