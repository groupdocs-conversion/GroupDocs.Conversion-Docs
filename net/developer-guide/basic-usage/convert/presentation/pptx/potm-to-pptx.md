---
id: potm-to-pptx
url: conversion/net/convert/potm-to-pptx
title: Convert POTM to PPTX
description: "POTM format represents Microsoft PowerPoint Template with .potm extension. Learn how to convert POTM to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTM to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with POTM extension are Microsoft PowerPoint template files with support for Macros. POTM files are created with PowerPoint 2007 or above and contains default settings that can be used to create further presentation files. These settings can include styles, backgrounds, colour palette, fonts and defaults along with macros that consist of custom functions for doing particular task. They may also be opened by a previous version of PowerPoint with Open XML document support installed. POTM files can be opened in Microsoft PowerPoint for editing like any other PowerPoint file.

## Steps to convert POTM to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTM file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.potm"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### POTM to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**POTM to PPTX converter**](https://products.groupdocs.app/conversion/potm-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTM to PPTX"](conversion/net/images/convert-to-pptx/convert-potm-to-pptx.png)](https://products.groupdocs.app/conversion/potm-to-pptx)