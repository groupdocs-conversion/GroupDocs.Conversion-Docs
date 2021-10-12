---
id: dwt-to-pptx
url: conversion/net/convert/dwt-to-pptx
title: Convert DWT to PPTX
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwt"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to PPTX converter**](https://products.groupdocs.app/conversion/dwt-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to PPTX"](conversion/net/images/convert-to-pptx/convert-dwt-to-pptx.png)](https://products.groupdocs.app/conversion/dwt-to-pptx)