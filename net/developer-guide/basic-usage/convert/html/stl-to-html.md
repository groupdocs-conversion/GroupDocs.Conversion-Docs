---
id: stl-to-html
url: conversion/net/convert/stl-to-html
title: Convert STL to HTML
description: "STL format represents Stereolithography with .stl extension. Learn how to convert STL to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert STL to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

STL, an abbreviation for stereolithography, is an interchangeable file format that represents 3-dimensional surface geometry. The file format finds its usage in several fields such as rapid prototyping, 3D printing, and computer-aided manufacturing. It represents a surface as a series of small triangles, known as facets, where each facet is described by a perpendicular direction and three points representing the vertices of the triangle.

## Steps to convert STL to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the STL file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source STL file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source STL file
using (var converter = new GroupDocs.Conversion.Converter("sample.stl"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### STL to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**STL to HTML converter**](https://products.groupdocs.app/conversion/stl-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert STL to HTML"](conversion/net/images/convert-to-html/convert-stl-to-html.png)](https://products.groupdocs.app/conversion/stl-to-html)