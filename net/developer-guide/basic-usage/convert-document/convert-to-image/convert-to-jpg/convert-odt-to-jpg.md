---
id: convert-odt-to-jpg
url: conversion/net/convert-odt-to-jpg
title: Convert ODT to JPG
description: "ODT format represents Open Document Text with .odt extension. Learn how to convert ODT to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODT to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google's web-based word processor included with Google Drive can open the ODT files for editing.

## Steps to convert ODT to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODT file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source ODT file
using (Converter converter = new Converter("sample.odt"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODT to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**ODT to JPG converter**](https://products.groupdocs.app/conversion/odt-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODT to JPG"](conversion/net/images/convert-to-jpg/convert-odt-to-jpg.png)](https://products.groupdocs.app/conversion/odt-to-jpg)