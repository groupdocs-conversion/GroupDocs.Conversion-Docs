---
id: convert-ai-to-ppt
url: conversion/net/convert-ai-to-ppt
title: Convert AI to PPT
description: "AI format represents Adobe Illustrator with .ai extension. Learn how to convert AI to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert AI to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with an .ai extension is an Adobe Illustrator Artwork file that contains vector graphics on a single page. It uses points to create paths for displaying the image data, thus making it safe from losing image quality if it is enlarged. AI format finds its major usage for logos and print media. AI files can be opened with Adobe Illustrator, Adobe Acrobat DC, PaintShop Pro, and CorelDraw Graphics tools.

## Steps to convert AI to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the AI file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source AI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source AI file
using (var converter = new GroupDocs.Conversion.Converter("sample.ai"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### AI to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**AI to PPT converter**](https://products.groupdocs.app/conversion/ai-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert AI to PPT"](conversion/net/images/convert-to-ppt/convert-ai-to-ppt.png)](https://products.groupdocs.app/conversion/ai-to-ppt)