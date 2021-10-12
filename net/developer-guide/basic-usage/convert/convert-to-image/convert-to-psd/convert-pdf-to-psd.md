---
id: convert-pdf-to-psd
url: conversion/net/convert-pdf-to-psd
title: Convert PDF to PSD
description: "PDF format represents Portable Document with .pdf extension. Learn how to convert PDF to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PDF to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

## Steps to convert PDF to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PDF file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PDF document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
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

### PDF to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**PDF to PSD converter**](https://products.groupdocs.app/conversion/pdf-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PDF to PSD"](conversion/net/images/convert-to-psd/convert-pdf-to-psd.png)](https://products.groupdocs.app/conversion/pdf-to-psd)