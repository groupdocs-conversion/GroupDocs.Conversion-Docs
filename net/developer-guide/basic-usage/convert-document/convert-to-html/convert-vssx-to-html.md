---
id: convert-vssx-to-html
url: conversion/net/convert-vssx-to-html
title: Convert VSSX to HTML
description: "VSSX format represents Visio Stencil File Format with .vssx extension. Learn how to convert VSSX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSX to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

## Steps to convert VSSX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.vssx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSSX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSX to HTML converter**](https://products.groupdocs.app/conversion/vssx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSX to HTML"](conversion/net/images/convert-to-html/convert-vssx-to-html.png)](https://products.groupdocs.app/conversion/vssx-to-html)