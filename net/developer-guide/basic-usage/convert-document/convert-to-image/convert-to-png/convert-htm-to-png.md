---
id: convert-htm-to-png
url: conversion/net/convert-htm-to-png
title: Convert HTM to PNG
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of HTM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (Converter converter = new Converter("sample.htm"))
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

### HTM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PNG converter**](https://products.groupdocs.app/conversion/htm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PNG"](conversion/net/images/convert-to-png/convert-htm-to-png.png)](https://products.groupdocs.app/conversion/htm-to-png)