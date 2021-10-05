---
id: convert-ppsm-to-ppt
url: conversion/net/convert-ppsm-to-ppt
title: Convert PPSM to PPT
description: "PPSM format represents Microsoft PowerPoint Slide Show with .ppsm extension. Learn how to convert PPSM to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPSM to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is PPTM which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as slide show, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening it in PowerPoint.

## Steps to convert PPSM to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPSM file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppsm"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPSM to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**PPSM to PPT converter**](https://products.groupdocs.app/conversion/ppsm-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPSM to PPT"](conversion/net/images/convert-to-ppt/convert-ppsm-to-ppt.png)](https://products.groupdocs.app/conversion/ppsm-to-ppt)