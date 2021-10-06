---
id: convert-eps-to-html
url: conversion/net/convert-eps-to-html
title: Convert EPS to HTML
description: "EPS format represents Encapsulated PostScript File with .eps extension. Learn how to convert EPS to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPS to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with EPS extension essentially describe an Encapsulated PostScript language program that describes the appearance of a single page. The name "Encapsulated" because it can be included or encapsulated in another PostScript language page description. This script based file format may contain any combination of text, graphics and images.

## Steps to convert EPS to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPS file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.eps"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EPS to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**EPS to HTML converter**](https://products.groupdocs.app/conversion/eps-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPS to HTML"](conversion/net/images/convert-to-html/convert-eps-to-html.png)](https://products.groupdocs.app/conversion/eps-to-html)