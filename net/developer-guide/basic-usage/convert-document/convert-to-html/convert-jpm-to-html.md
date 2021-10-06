---
id: convert-jpm-to-html
url: conversion/net/convert-jpm-to-html
title: Convert JPM to HTML
description: "JPM format represents JPEG 2000 Image File with .jpm extension. Learn how to convert JPM to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPM to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPM is an extension to the JP2 format and was developed for multi-page documents with multiple objects per page.

## Steps to convert JPM to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPM file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPM file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpm"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPM to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**JPM to HTML converter**](https://products.groupdocs.app/conversion/jpm-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPM to HTML"](conversion/net/images/convert-to-html/convert-jpm-to-html.png)](https://products.groupdocs.app/conversion/jpm-to-html)