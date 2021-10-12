---
id: cdr-to-html
url: conversion/net/convert/cdr-to-html
title: Convert CDR to HTML
description: "CDR format represents CorelDraw Vector Graphic Drawing with .cdr extension. Learn how to convert CDR to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CDR to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A CDR file is a vector drawing image file that is natively created with CorelDRAW for storing digital images encoded and compressed. Such a drawing file contains text, lines, shapes, images, colors, and effects for vector representation of image contents. It can be used for the representation of various graphics data like brochures, tabloids, envelopes, and postcards. Besides CorelDRAW, other Corel products such as Corel Paintshop Pro and CorelDRAW Graphics suite can also open the CDR file formats.

## Steps to convert CDR to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CDR file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CDR file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CDR file
using (var converter = new GroupDocs.Conversion.Converter("sample.cdr"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CDR to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**CDR to HTML converter**](https://products.groupdocs.app/conversion/cdr-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CDR to HTML"](conversion/net/images/convert-to-html/convert-cdr-to-html.png)](https://products.groupdocs.app/conversion/cdr-to-html)