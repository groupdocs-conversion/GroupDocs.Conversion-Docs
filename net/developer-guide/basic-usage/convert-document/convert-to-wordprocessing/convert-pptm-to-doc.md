---
id: convert-pptm-to-doc
url: conversion/net/convert-pptm-to-doc
title: Convert PPTM to DOC
description: "PPTM format represents Microsoft PowerPoint Presentation with .pptm extension. Learn how to convert PPTM to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTM to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can't execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

## Steps to convert PPTM to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTM file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptm"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to DOC converter**](https://products.groupdocs.app/conversion/pptm-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to DOC"](conversion/net/images/convert-pptm-to-doc.png)](https://products.groupdocs.app/conversion/pptm-to-doc)