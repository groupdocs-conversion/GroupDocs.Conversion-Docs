---
id: convert-xlsb-to-jpg
url: conversion/net/convert-xlsb-to-jpg
title: Convert XLSB to JPG
description: "XLSB format represents Microsoft Excel Binary Spreadsheet File with .xlsb extension. Learn how to convert XLSB to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSB to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLSB file format specifies the Excel Binary File Format, which is a collection of records and structures that specify Excel workbook content. The content can include unstructured or semi-structured tables of numbers, text, or both numbers and text, formulas, external data connections, charts and images. Unlike XLSX (which is based on Open XML file format), the XLSB represents binary Excel workbook file.

## Steps to convert XLSB to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSB file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source XLSB file
using (Converter converter = new Converter("sample.xlsb"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSB to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSB to JPG converter**](https://products.groupdocs.app/conversion/xlsb-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSB to JPG"](conversion/net/images/convert-to-jpg/convert-xlsb-to-jpg.png)](https://products.groupdocs.app/conversion/xlsb-to-jpg)