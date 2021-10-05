---
id: convert-xlt-to-ppt
url: conversion/net/convert-xlt-to-ppt
title: Convert XLT to PPT
description: "XLT format represents Microsoft Excel Template with .xlt extension. Learn how to convert XLT to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLT to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

## Steps to convert XLT to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLT file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLT file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlt"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLT to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**XLT to PPT converter**](https://products.groupdocs.app/conversion/xlt-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLT to PPT"](conversion/net/images/convert-to-ppt/convert-xlt-to-ppt.png)](https://products.groupdocs.app/conversion/xlt-to-ppt)