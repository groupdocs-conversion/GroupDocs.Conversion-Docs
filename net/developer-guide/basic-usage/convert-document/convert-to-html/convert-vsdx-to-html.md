---
id: convert-vsdx-to-html
url: conversion/net/convert-vsdx-to-html
title: Convert VSDX to HTML
description: "VSDX format represents Microsoft Visio File Format with .vsdx extension. Learn how to convert VSDX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDX to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

## Steps to convert VSDX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vsdx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to HTML converter**](https://products.groupdocs.app/conversion/vsdx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to HTML"](conversion/net/images/convert-to-html/convert-vsdx-to-html.png)](https://products.groupdocs.app/conversion/vsdx-to-html)