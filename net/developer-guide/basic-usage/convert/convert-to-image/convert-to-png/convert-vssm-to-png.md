---
id: convert-vssm-to-png
url: conversion/net/convert-vssm-to-png
title: Convert VSSM to PNG
description: "VSSM format represents Microsoft Visio Macro Enabled File Format with .vssm extension. Learn how to convert VSSM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSM extension are Microsoft Visio Stencil files that support provide support for macros. A VSSM file when opened allows running the macros to achieve the desired formatting and placement of shapes in a diagram. In general, Microsoft Visio is drawing software that allows creating files that can contain and represent user-defined information in different shapes.

## Steps to convert VSSM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSSM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSSM file
using (Converter converter = new Converter("sample.vssm"))
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

### VSSM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSM to PNG converter**](https://products.groupdocs.app/conversion/vssm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSM to PNG"](conversion/net/images/convert-to-png/convert-vssm-to-png.png)](https://products.groupdocs.app/conversion/vssm-to-png)