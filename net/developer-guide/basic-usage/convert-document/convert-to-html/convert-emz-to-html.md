---
id: convert-emz-to-html
url: conversion/net/convert-emz-to-html
title: Convert EMZ to HTML
description: "EMZ format represents Enhanced Windows Metafile Compressed with .emz extension. Learn how to convert EMZ to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMZ to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .emz extension is a compressed container of Enhanced Metafile (.emf file). It follows GZIP compression algorithm and takes less storage space due to compression. The small file size makes it more easy to transfer EMZ files over the network.

## Steps to convert EMZ to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMZ file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMZ file
using (var converter = new GroupDocs.Conversion.Converter("sample.emz"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMZ to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to HTML converter**](https://products.groupdocs.app/conversion/emz-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to HTML"](conversion/net/images/convert-to-html/convert-emz-to-html.png)](https://products.groupdocs.app/conversion/emz-to-html)