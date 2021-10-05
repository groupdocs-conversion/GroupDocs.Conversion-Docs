---
id: convert-mht-to-ppt
url: conversion/net/convert-mht-to-ppt
title: Convert MHT to PPT
description: "MHT format represents MIME Encapsulation of Aggregate HTML with .mht extension. Learn how to convert MHT to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MHT to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with MHT extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on.

## Steps to convert MHT to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MHT file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MHT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MHT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mht"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MHT to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**MHT to PPT converter**](https://products.groupdocs.app/conversion/mht-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MHT to PPT"](conversion/net/images/convert-to-ppt/convert-mht-to-ppt.png)](https://products.groupdocs.app/conversion/mht-to-ppt)