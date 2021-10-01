---
id: convert-dwg-to-txt
url: conversion/net/convert-dwg-to-txt
title: Convert DWG to TXT
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to TXT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to TXT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to TXT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to TXT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt`
* Call `Converter` class `Convert` method and pass the filename for the converted TXT file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to TXT Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to TXT converter**](https://products.groupdocs.app/conversion/dwg-to-txt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to TXT"](conversion/net/images/convert-to-txt/convert-dwg-to-txt.png)](https://products.groupdocs.app/conversion/dwg-to-txt)