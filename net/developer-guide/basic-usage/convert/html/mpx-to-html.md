---
id: mpx-to-html
url: conversion/net/convert/mpx-to-html
title: Convert MPX to HTML
description: "MPX format represents Microsoft Project Exchange File with .mpx extension. Learn how to convert MPX to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPX to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MPX, Microsoft Exchange File Format, is an ASCII file format for transferring project information between Microsoft Project (MSP) and other applications that support the MPX file format such as Primavera Project Planner, Sciforma, and Timberline Precision Estimating. The MPX file format allows you to transfer project information that cannot appear in a table, such as detailed resource assignment information, calendar information, or information in the Project Info dialog box.

## Steps to convert MPX to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPX file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpx"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPX to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**MPX to HTML converter**](https://products.groupdocs.app/conversion/mpx-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPX to HTML"](conversion/net/images/convert-to-html/convert-mpx-to-html.png)](https://products.groupdocs.app/conversion/mpx-to-html)