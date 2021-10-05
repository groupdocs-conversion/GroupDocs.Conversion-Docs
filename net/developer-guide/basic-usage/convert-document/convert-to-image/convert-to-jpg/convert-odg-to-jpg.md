---
id: convert-odg-to-jpg
url: conversion/net/convert-odg-to-jpg
title: Convert ODG to JPG
description: "ODG format represents OpenDocument Drawing File with .odg extension. Learn how to convert ODG to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODG to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The ODG file format is used by Apache OpenOffice's Draw application to store drawing elements as a vector image. It follows the XML based file format specifications outlined by Advancement of Structural Information Standards (OASIS). ODG represents drawings as vector images using points, lines and curves. Besides OpenOffice, LibreOffice and other applications also provide support for working with ODG file format. Other formats supported by OpenOffice, for example, include ODT, ODF, ODP and ODS.

## Steps to convert ODG to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODG file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source ODG file
using (Converter converter = new Converter("sample.odg"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODG to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**ODG to JPG converter**](https://products.groupdocs.app/conversion/odg-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODG to JPG"](conversion/net/images/convert-to-jpg/convert-odg-to-jpg.png)](https://products.groupdocs.app/conversion/odg-to-jpg)