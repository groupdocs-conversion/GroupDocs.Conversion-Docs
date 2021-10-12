---
id: pot-to-png
url: conversion/net/convert/pot-to-png
title: Convert POT to PNG
description: "POT format represents PowerPoint Template with .pot extension. Learn how to convert POT to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POT to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POT extension represent Microsoft PowerPoint template files created by PowerPoint 97-2003 versions. Files created with these versions of Microsoft PowerPoint are in binary format as compared to those created in Office OpenXML file formats using the higher versions of PowerPoint. The files, hence, generated can be used to create presentations that have the same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, color palettes, fonts, and defaults.

## Steps to convert POT to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POT file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of POT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POT file
using (Converter converter = new Converter("sample.pot"))
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

### POT to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**POT to PNG converter**](https://products.groupdocs.app/conversion/pot-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POT to PNG"](conversion/net/images/convert-to-png/convert-pot-to-png.png)](https://products.groupdocs.app/conversion/pot-to-png)