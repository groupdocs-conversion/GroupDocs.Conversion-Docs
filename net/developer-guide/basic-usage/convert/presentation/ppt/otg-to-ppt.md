---
id: otg-to-ppt
url: conversion/net/convert/otg-to-ppt
title: Convert OTG to PPT
description: "OTG format represents OpenDocument Graphic Template with .otg extension. Learn how to convert OTG to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTG to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An OTG file is a drawing template that is created using the OpenDocument standard that follows the OASIS Office Applications 1.0 specification. It represents the default organization of drawing elements for a vector image that can be used to further enhance the contents of the file.

## Steps to convert OTG to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTG file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTG file
using (var converter = new GroupDocs.Conversion.Converter("sample.otg"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTG to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**OTG to PPT converter**](https://products.groupdocs.app/conversion/otg-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTG to PPT"](conversion/net/images/convert-to-ppt/convert-otg-to-ppt.png)](https://products.groupdocs.app/conversion/otg-to-ppt)