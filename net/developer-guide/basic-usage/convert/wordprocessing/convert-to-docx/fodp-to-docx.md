---
id: fodp-to-docx
url: conversion/net/convert/fodp-to-docx
title: Convert FODP to DOCX
description: "FODP format represents OpenDocument Flat XML Presentation with .fodp extension. Learn how to convert FODP to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODP to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODP is a file format for the presentations saved in OpenDocument format.

## Steps to convert FODP to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODP file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODP file
using (var converter = new GroupDocs.Conversion.Converter("sample.fodp"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### FODP to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**FODP to DOCX converter**](https://products.groupdocs.app/conversion/fodp-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODP to DOCX"](conversion/net/images/convert-to-docx/convert-fodp-to-docx.png)](https://products.groupdocs.app/conversion/fodp-to-docx)