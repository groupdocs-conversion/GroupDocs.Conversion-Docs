---
id: xps-to-html
url: conversion/net/convert/xps-to-html
title: Convert XPS to HTML
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xps"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to HTML converter**](https://products.groupdocs.app/conversion/xps-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to HTML"](conversion/net/images/convert-to-html/convert-xps-to-html.png)](https://products.groupdocs.app/conversion/xps-to-html)