---
id: convert-ods-to-jpg
url: conversion/net/convert-ods-to-jpg
title: Convert ODS to JPG
description: "ODS format represents Open Document Spreadsheet with .ods extension. Learn how to convert ODS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODS extension stand for OpenDocument Spreadsheet Document format that is editable by the user. Data is stored inside the ODF file into rows and columns. It is an XML-based format and is one of the several subtypes in the Open Document Formats (ODF) family. The format is specified as part of the ODF 1.2 specifications published and maintained by OASIS.

## Steps to convert ODS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source ODS file
using (Converter converter = new Converter("sample.ods"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**ODS to JPG converter**](https://products.groupdocs.app/conversion/ods-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODS to JPG"](conversion/net/images/convert-to-jpg/convert-ods-to-jpg.png)](https://products.groupdocs.app/conversion/ods-to-jpg)