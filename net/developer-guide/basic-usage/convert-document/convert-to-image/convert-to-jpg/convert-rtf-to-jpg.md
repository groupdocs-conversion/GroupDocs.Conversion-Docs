---
id: convert-rtf-to-jpg
url: conversion/net/convert-rtf-to-jpg
title: Convert RTF to JPG
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source RTF file
using (Converter converter = new Converter("sample.rtf"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to JPG converter**](https://products.groupdocs.app/conversion/rtf-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to JPG"](conversion/net/images/convert-to-jpg/convert-rtf-to-jpg.png)](https://products.groupdocs.app/conversion/rtf-to-jpg)