---
id: dwg-to-pptx
url: conversion/net/convert/dwg-to-pptx
title: Convert DWG to PPTX
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to PPTX converter**](https://products.groupdocs.app/conversion/dwg-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to PPTX"](conversion/net/images/convert-to-pptx/convert-dwg-to-pptx.png)](https://products.groupdocs.app/conversion/dwg-to-pptx)