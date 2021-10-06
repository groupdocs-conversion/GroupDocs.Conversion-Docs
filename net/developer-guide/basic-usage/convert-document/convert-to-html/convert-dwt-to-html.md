---
id: convert-dwt-to-html
url: conversion/net/convert-dwt-to-html
title: Convert DWT to HTML
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwt"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to HTML converter**](https://products.groupdocs.app/conversion/dwt-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to HTML"](conversion/net/images/convert-to-html/convert-dwt-to-html.png)](https://products.groupdocs.app/conversion/dwt-to-html)