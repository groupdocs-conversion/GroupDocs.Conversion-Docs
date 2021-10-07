---
id: convert-md-to-psd
url: conversion/net/convert-md-to-psd
title: Convert MD to PSD
description: "MD format represents Markdown with .md extension. Learn how to convert MD to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

## Steps to convert MD to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MD file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MD document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MD file
using (Converter converter = new Converter("sample.md"))
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

### MD to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**MD to PSD converter**](https://products.groupdocs.app/conversion/md-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to PSD"](conversion/net/images/convert-to-psd/convert-md-to-psd.png)](https://products.groupdocs.app/conversion/md-to-psd)