---
id: convert-pptm-to-jpg
url: conversion/net/convert-pptm-to-jpg
title: Convert PPTM to JPG
description: "PPTM format represents Microsoft PowerPoint Presentation with .pptm extension. Learn how to convert PPTM to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTM to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can't execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

## Steps to convert PPTM to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTM file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPTM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTM file
using (Converter converter = new Converter("sample.pptm"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPTM to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to JPG converter**](https://products.groupdocs.app/conversion/pptm-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to JPG"](conversion/net/images/convert-to-jpg/convert-pptm-to-jpg.png)](https://products.groupdocs.app/conversion/pptm-to-jpg)