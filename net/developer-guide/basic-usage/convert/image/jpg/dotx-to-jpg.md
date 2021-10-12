---
id: dotx-to-jpg
url: conversion/net/convert/dotx-to-jpg
title: Convert DOTX to JPG
description: "DOTX format represents Word Open XML Document Template with .dotx extension. Learn how to convert DOTX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOTX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DOTX extension are template files created by Microsoft Word to have pre-formatted settings for a generation of further DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from this template. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOTX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOTX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DOTX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOTX file
using (Converter converter = new Converter("sample.dotx"))
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

### DOTX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DOTX to JPG converter**](https://products.groupdocs.app/conversion/dotx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOTX to JPG"](conversion/net/images/convert-to-jpg/convert-dotx-to-jpg.png)](https://products.groupdocs.app/conversion/dotx-to-jpg)