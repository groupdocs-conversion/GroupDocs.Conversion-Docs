---
id: convert-xps-to-png
url: conversion/net/convert-xps-to-png
title: Convert XPS to PNG
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of XPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (Converter converter = new Converter("sample.xps"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to PNG converter**](https://products.groupdocs.app/conversion/xps-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to PNG"](conversion/net/images/convert-to-png/convert-xps-to-png.png)](https://products.groupdocs.app/conversion/xps-to-png)