---
id: convert-odg-to-html
url: conversion/net/convert-odg-to-html
title: Convert ODG to HTML
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

## Steps to convert ODG to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODG file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODG file
using (var converter = new GroupDocs.Conversion.Converter("sample.odg"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODG to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to HTML converter**](https://products.groupdocs.app/conversion/odg-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to HTML"](conversion/net/images/convert-to-html/convert-odg-to-html.png)](https://products.groupdocs.app/conversion/odg-to-html)