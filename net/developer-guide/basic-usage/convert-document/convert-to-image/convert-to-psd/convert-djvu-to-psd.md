---
id: convert-djvu-to-psd
url: conversion/net/convert-djvu-to-psd
title: Convert DJVU to PSD
description: "DJVU format represents Graphics File format with .djvu extension. Learn how to convert DJVU to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DJVU to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DjVu, pronounced as “déjà vu”, is a graphics file format intended for scanned documents and books especially those which contain the combination of text, drawings, images and photographs. It was developed by AT&T Labs. It uses multiple techniques like image layer separation of text and background images, progressive loading, arithmetic coding and lossy compression for bitonal images.

## Steps to convert DJVU to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DJVU file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DJVU file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DJVU document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DJVU file
using (Converter converter = new Converter("sample.djvu"))
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

### DJVU to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**DJVU to PSD converter**](https://products.groupdocs.app/conversion/djvu-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DJVU to PSD"](conversion/net/images/convert-to-psd/convert-djvu-to-psd.png)](https://products.groupdocs.app/conversion/djvu-to-psd)