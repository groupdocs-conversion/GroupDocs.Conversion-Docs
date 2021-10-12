---
id: convert-pot-to-ppt
url: conversion/net/convert-pot-to-ppt
title: Convert POT to PPT
description: "POT format represents PowerPoint Template with .pot extension. Learn how to convert POT to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POT to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POT extension represent Microsoft PowerPoint template files created by PowerPoint 97-2003 versions. Files created with these versions of Microsoft PowerPoint are in binary format as compared to those created in Office OpenXML file formats using the higher versions of PowerPoint. The files, hence, generated can be used to create presentations that have the same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, color palettes, fonts, and defaults.

## Steps to convert POT to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POT file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POT file
using (var converter = new GroupDocs.Conversion.Converter("sample.pot"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POT to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**POT to PPT converter**](https://products.groupdocs.app/conversion/pot-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POT to PPT"](conversion/net/images/convert-to-ppt/convert-pot-to-ppt.png)](https://products.groupdocs.app/conversion/pot-to-ppt)