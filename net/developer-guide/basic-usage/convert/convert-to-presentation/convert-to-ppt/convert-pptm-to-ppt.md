---
id: convert-pptm-to-ppt
url: conversion/net/convert-pptm-to-ppt
title: Convert PPTM to PPT
description: "PPTM format represents Microsoft PowerPoint Presentation with .pptm extension. Learn how to convert PPTM to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTM to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can't execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

## Steps to convert PPTM to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTM file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptm"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPTM to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to PPT converter**](https://products.groupdocs.app/conversion/pptm-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to PPT"](conversion/net/images/convert-to-ppt/convert-pptm-to-ppt.png)](https://products.groupdocs.app/conversion/pptm-to-ppt)