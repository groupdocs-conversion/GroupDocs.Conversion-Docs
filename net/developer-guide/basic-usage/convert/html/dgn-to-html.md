---
id: dgn-to-html
url: conversion/net/convert/dgn-to-html
title: Convert DGN to HTML
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (var converter = new GroupDocs.Conversion.Converter("sample.dgn"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DGN to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to HTML converter**](https://products.groupdocs.app/conversion/dgn-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to HTML"](conversion/net/images/convert-to-html/convert-dgn-to-html.png)](https://products.groupdocs.app/conversion/dgn-to-html)