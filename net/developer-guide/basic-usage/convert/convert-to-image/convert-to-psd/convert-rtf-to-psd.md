---
id: convert-rtf-to-psd
url: conversion/net/convert-rtf-to-psd
title: Convert RTF to PSD
description: "RTF format represents Rich Text File Format with .rtf extension. Learn how to convert RTF to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert RTF to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

## Steps to convert RTF to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the RTF file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of RTF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source RTF file
using (Converter converter = new Converter("sample.rtf"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### RTF to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**RTF to PSD converter**](https://products.groupdocs.app/conversion/rtf-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert RTF to PSD"](conversion/net/images/convert-to-psd/convert-rtf-to-psd.png)](https://products.groupdocs.app/conversion/rtf-to-psd)