---
id: convert-vsdx-to-png
url: conversion/net/convert-vsdx-to-png
title: Convert VSDX to PNG
description: "VSDX format represents Microsoft Visio File Format with .vsdx extension. Learn how to convert VSDX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSDX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

## Steps to convert VSDX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSDX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSDX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSDX file
using (Converter converter = new Converter("sample.vsdx"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSDX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSDX to PNG converter**](https://products.groupdocs.app/conversion/vsdx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSDX to PNG"](conversion/net/images/convert-to-png/convert-vsdx-to-png.png)](https://products.groupdocs.app/conversion/vsdx-to-png)