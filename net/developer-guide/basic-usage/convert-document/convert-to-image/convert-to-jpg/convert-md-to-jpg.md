---
id: convert-md-to-jpg
url: conversion/net/convert-md-to-jpg
title: Convert MD to JPG
description: "MD format represents Markdown with .md extension. Learn how to convert MD to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MD to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Text files created with Markdown language dialects is saved with .MD or .MARKDOWN file extension. MD files are saved in plain text format that uses Markdown language which also includes inline text symbols, defining how a text can be formatted such as indentations, table formatting, fonts, and headers.  MD files can be converted to HTML with a program called Markdown. Markdown language is released by John Gruber.

## Steps to convert MD to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MD file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MD file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source MD file
using (Converter converter = new Converter("sample.md"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MD to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**MD to JPG converter**](https://products.groupdocs.app/conversion/md-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MD to JPG"](conversion/net/images/convert-to-jpg/convert-md-to-jpg.png)](https://products.groupdocs.app/conversion/md-to-jpg)