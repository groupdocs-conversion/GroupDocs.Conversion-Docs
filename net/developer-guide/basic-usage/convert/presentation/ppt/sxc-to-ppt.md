---
id: sxc-to-ppt
url: conversion/net/convert/sxc-to-ppt
title: Convert SXC to PPT
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to PPT converter**](https://products.groupdocs.app/conversion/sxc-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to PPT"](conversion/net/images/convert-to-ppt/convert-sxc-to-ppt.png)](https://products.groupdocs.app/conversion/sxc-to-ppt)