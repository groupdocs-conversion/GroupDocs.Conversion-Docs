---
id: convert-dng-to-docx
url: conversion/net/convert-dng-to-docx
title: Convert DNG to DOCX
description: "DNG format represents Digital Camera Image Format with .dng extension. Learn how to convert DNG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DNG to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DNG is a digital camera image format used for the storage of raw files. It has been developed by Adobe in September 2004. It was basically developed for digital photography. DNG is an extension of TIFF/EP standard format and uses metadata significantly. In order to manipulate raw data from digital cameras with ease of flexibility and artistic control, photographers opt camera raw files.

## Steps to convert DNG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DNG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DNG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dng"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DNG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**DNG to DOCX converter**](https://products.groupdocs.app/conversion/dng-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DNG to DOCX"](conversion/net/images/convert-to-docx/convert-dng-to-docx.png)](https://products.groupdocs.app/conversion/dng-to-docx)