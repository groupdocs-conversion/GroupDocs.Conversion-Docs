---
id: convert-dotm-to-png
url: conversion/net/convert-dotm-to-png
title: Convert DOTM to PNG
description: "DOTM format represents Microsoft Word Macro-Enabled Template with .dotm extension. Learn how to convert DOTM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with DOTM extension represents template file created with Microsoft Word 2007 or higher. It is similar to the popular DOCX file format other than it retains the user defined settings for reuse in case of creating new documents. Such documents are more often used in offices where a standard template file is generated with settings like page information, margins, default layout and macros, and is used to create new documents from it when required. DOTM files, however, save macros, that are a series of commands in the form of recorded actions for automatic completion of a task. This helps save time in carrying out actions that are repeated in completion of a task.

## Steps to convert DOTM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DOTM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTM file
using (Converter converter = new Converter("sample.dotm"))
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

### DOTM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTM to PNG converter**](https://products.groupdocs.app/conversion/dotm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTM to PNG"](conversion/net/images/convert-to-png/convert-dotm-to-png.png)](https://products.groupdocs.app/conversion/dotm-to-png)