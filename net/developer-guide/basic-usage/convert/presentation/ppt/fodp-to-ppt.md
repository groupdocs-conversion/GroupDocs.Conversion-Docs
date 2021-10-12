---
id: fodp-to-ppt
url: conversion/net/convert/fodp-to-ppt
title: Convert FODP to PPT
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to PPT converter**](https://products.groupdocs.app/conversion/fodp-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to PPT"](conversion/net/images/convert-to-ppt/convert-fodp-to-ppt.png)](https://products.groupdocs.app/conversion/fodp-to-ppt)