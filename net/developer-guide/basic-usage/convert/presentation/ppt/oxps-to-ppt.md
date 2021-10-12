---
id: oxps-to-ppt
url: conversion/net/convert/oxps-to-ppt
title: Convert OXPS to PPT
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

## Steps to convert OXPS to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OXPS file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OXPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OXPS file
using (var converter = new GroupDocs.Conversion.Converter("sample.oxps"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OXPS to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to PPT converter**](https://products.groupdocs.app/conversion/oxps-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to PPT"](conversion/net/images/convert-to-ppt/convert-oxps-to-ppt.png)](https://products.groupdocs.app/conversion/oxps-to-ppt)