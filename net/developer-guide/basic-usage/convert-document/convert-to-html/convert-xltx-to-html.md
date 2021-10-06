---
id: convert-xltx-to-html
url: conversion/net/convert-xltx-to-html
title: Convert XLTX to HTML
description: "XLTX format represents Microsoft Excel Open XML Template with .xltx extension. Learn how to convert XLTX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLTX to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLTX extension represent Microsoft Excel Template files that are based on the Office OpenXML file format specifications. It is used to create a standard template file that can be utilized to generate XLSX files that exhibit the same settings as specified in the XLTX file.

## Steps to convert XLTX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLTX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xltx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLTX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**XLTX to HTML converter**](https://products.groupdocs.app/conversion/xltx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLTX to HTML"](conversion/net/images/convert-to-html/convert-xltx-to-html.png)](https://products.groupdocs.app/conversion/xltx-to-html)