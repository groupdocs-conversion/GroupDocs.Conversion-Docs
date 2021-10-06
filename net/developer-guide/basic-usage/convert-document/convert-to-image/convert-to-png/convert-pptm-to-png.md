---
id: convert-pptm-to-png
url: conversion/net/convert-pptm-to-png
title: Convert PPTM to PNG
description: "PPTM format represents Microsoft PowerPoint Presentation with .pptm extension. Learn how to convert PPTM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can't execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

## Steps to convert PPTM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPTM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTM file
using (Converter converter = new Converter("sample.pptm"))
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

### PPTM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to PNG converter**](https://products.groupdocs.app/conversion/pptm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to PNG"](conversion/net/images/convert-to-png/convert-pptm-to-png.png)](https://products.groupdocs.app/conversion/pptm-to-png)