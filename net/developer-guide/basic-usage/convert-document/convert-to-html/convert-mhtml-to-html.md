---
id: convert-mhtml-to-html
url: conversion/net/convert-mhtml-to-html
title: Convert MHTML to HTML
description: "MHTML format represents MIME Encapsulation of Aggregate HTML with .mhtml extension. Learn how to convert MHTML to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHTML to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

## Steps to convert MHTML to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHTML file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHTML file
using (var converter = new GroupDocs.Conversion.Converter("sample.mhtml"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHTML to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**MHTML to HTML converter**](https://products.groupdocs.app/conversion/mhtml-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHTML to HTML"](conversion/net/images/convert-to-html/convert-mhtml-to-html.png)](https://products.groupdocs.app/conversion/mhtml-to-html)