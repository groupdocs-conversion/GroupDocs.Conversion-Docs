---
id: convert-xltx-to-jpg
url: conversion/net/convert-xltx-to-jpg
title: Convert XLTX to JPG
description: "XLTX format represents Microsoft Excel Open XML Template with .xltx extension. Learn how to convert XLTX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLTX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLTX extension represent Microsoft Excel Template files that are based on the Office OpenXML file format specifications. It is used to create a standard template file that can be utilized to generate XLSX files that exhibit the same settings as specified in the XLTX file.

## Steps to convert XLTX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLTX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source XLTX file
using (Converter converter = new Converter("sample.xltx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLTX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**XLTX to JPG converter**](https://products.groupdocs.app/conversion/xltx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLTX to JPG"](conversion/net/images/convert-to-jpg/convert-xltx-to-jpg.png)](https://products.groupdocs.app/conversion/xltx-to-jpg)