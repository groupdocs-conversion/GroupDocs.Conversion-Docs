---
id: convert-mht-to-html
url: conversion/net/convert-mht-to-html
title: Convert MHT to HTML
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mht"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHT to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to HTML converter**](https://products.groupdocs.app/conversion/mht-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to HTML"](conversion/net/images/convert-to-html/convert-mht-to-html.png)](https://products.groupdocs.app/conversion/mht-to-html)