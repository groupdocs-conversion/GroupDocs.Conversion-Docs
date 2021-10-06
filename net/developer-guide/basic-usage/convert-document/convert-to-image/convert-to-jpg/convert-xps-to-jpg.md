---
id: convert-xps-to-jpg
url: conversion/net/convert-xps-to-jpg
title: Convert XPS to JPG
description: "XPS format represents Open XML Paper Specification with .xps extension. Learn how to convert XPS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XPS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

## Steps to convert XPS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XPS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of XPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XPS file
using (Converter converter = new Converter("sample.xps"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XPS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**XPS to JPG converter**](https://products.groupdocs.app/conversion/xps-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XPS to JPG"](conversion/net/images/convert-to-jpg/convert-xps-to-jpg.png)](https://products.groupdocs.app/conversion/xps-to-jpg)