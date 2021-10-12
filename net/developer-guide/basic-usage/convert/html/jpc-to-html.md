---
id: jpc-to-html
url: conversion/net/convert/jpc-to-html
title: Convert JPC to HTML
description: "JPC format represents JPEG 2000 Image File with .jpc extension. Learn how to convert JPC to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPC to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A JPC file is an image that is compressed using wavelet compression instead of DCT compression format defined in Part 1 of the JPEG 2000 standard.

## Steps to convert JPC to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPC file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPC file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpc"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPC to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**JPC to HTML converter**](https://products.groupdocs.app/conversion/jpc-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPC to HTML"](conversion/net/images/convert-to-html/convert-jpc-to-html.png)](https://products.groupdocs.app/conversion/jpc-to-html)