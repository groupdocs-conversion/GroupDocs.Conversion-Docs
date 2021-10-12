---
id: epub-to-jpg
url: conversion/net/convert/epub-to-jpg
title: Convert EPUB to JPG
description: "EPUB format represents Digital E-Book File Format with .epub extension. Learn how to convert EPUB to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EPUB to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

## Steps to convert EPUB to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EPUB file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of EPUB document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EPUB file
using (Converter converter = new Converter("sample.epub"))
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

### EPUB to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EPUB to JPG converter**](https://products.groupdocs.app/conversion/epub-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EPUB to JPG"](conversion/net/images/convert-to-jpg/convert-epub-to-jpg.png)](https://products.groupdocs.app/conversion/epub-to-jpg)