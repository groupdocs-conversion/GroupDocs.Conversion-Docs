---
id: convert-htm-to-ppt
url: conversion/net/convert-htm-to-ppt
title: Convert HTM to PPT
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.htm"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PPT converter**](https://products.groupdocs.app/conversion/htm-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PPT"](conversion/net/images/convert-to-ppt/convert-htm-to-ppt.png)](https://products.groupdocs.app/conversion/htm-to-ppt)