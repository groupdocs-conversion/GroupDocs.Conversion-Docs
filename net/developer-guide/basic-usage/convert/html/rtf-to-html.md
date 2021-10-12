---
id: rtf-to-html
url: conversion/net/convert/rtf-to-html
title: Convert RTF to HTML
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source RTF file
using (var converter = new GroupDocs.Conversion.Converter("sample.rtf"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to HTML converter**](https://products.groupdocs.app/conversion/rtf-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to HTML"](conversion/net/images/convert-to-html/convert-rtf-to-html.png)](https://products.groupdocs.app/conversion/rtf-to-html)