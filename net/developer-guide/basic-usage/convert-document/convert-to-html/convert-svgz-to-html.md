---
id: convert-svgz-to-html
url: conversion/net/convert-svgz-to-html
title: Convert SVGZ to HTML
description: "SVGZ format represents Compressed Scalable Vector Graphics File with .svgz extension. Learn how to convert SVGZ to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SVGZ to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .svgz extension is a compressed version of Scalable Vector Graphics (.SVG) file. It is compressed with gzip compression and contains data in XML format. SVGZ files support transparency, gradients, animations, and filters. SVGZ files are smaller in size as compared to the default SVG files and this reduced file size helps transfer the graphics files.

## Steps to convert SVGZ to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SVGZ file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SVGZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SVGZ file
using (var converter = new GroupDocs.Conversion.Converter("sample.svgz"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SVGZ to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**SVGZ to HTML converter**](https://products.groupdocs.app/conversion/svgz-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SVGZ to HTML"](conversion/net/images/convert-to-html/convert-svgz-to-html.png)](https://products.groupdocs.app/conversion/svgz-to-html)