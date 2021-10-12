---
id: convert-docm-to-png
url: conversion/net/convert-docm-to-png
title: Convert DOCM to PNG
description: "DOCM format represents Microsoft Word Macro-Enabled Document with .docm extension. Learn how to convert DOCM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOCM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DOCM files are Microsoft Word 2007 or higher generated documents with the ability to run macros. It is similar to DOCX file format but the ability to run macros makes it different from DOCX. Like DOCX, DOCM files can be store text, images, tables, shapes, charts and other contents. The capability to run macros make it easy to save time by executing the series of commands in the form of recorded actions for automatic completion of a task. DOCM files can be opened and edited in Microsoft Word 2007 and above.

## Steps to convert DOCM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOCM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DOCM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOCM file
using (Converter converter = new Converter("sample.docm"))
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

### DOCM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DOCM to PNG converter**](https://products.groupdocs.app/conversion/docm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOCM to PNG"](conversion/net/images/convert-to-png/convert-docm-to-png.png)](https://products.groupdocs.app/conversion/docm-to-png)