---
id: convert-docm-to-html
url: conversion/net/convert-docm-to-html
title: Convert DOCM to HTML
description: "DOCM format represents Microsoft Word Macro-Enabled Document with .docm extension. Learn how to convert DOCM to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCM to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DOCM files are Microsoft Word 2007 or higher generated documents with the ability to run macros. It is similar to DOCX file format but the ability to run macros makes it different from DOCX. Like DOCX, DOCM files can be store text, images, tables, shapes, charts and other contents. The capability to run macros make it easy to save time by executing the series of commands in the form of recorded actions for automatic completion of a task. DOCM files can be opened and edited in Microsoft Word 2007 and above.

## Steps to convert DOCM to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCM file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCM file
using (var converter = new GroupDocs.Conversion.Converter("sample.docm"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DOCM to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCM to HTML converter**](https://products.groupdocs.app/conversion/docm-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCM to HTML"](conversion/net/images/convert-to-html/convert-docm-to-html.png)](https://products.groupdocs.app/conversion/docm-to-html)