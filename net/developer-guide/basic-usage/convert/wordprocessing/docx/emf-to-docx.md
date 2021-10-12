---
id: emf-to-docx
url: conversion/net/convert/emf-to-docx
title: Convert EMF to DOCX
description: "EMF format represents Enhanced Metafile Format with .emf extension. Learn how to convert EMF to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMF to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Enhanced metafile format (EMF) stores graphical images device-independently. Metafiles of EMF comprises of variable-length records in chronological order that can render the stored image after parsing on any output device. These variable-length records can be definitions of enclosed objects, commands for drawing, and graphics properties critical to render the image accurately.

## Steps to convert EMF to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMF file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EMF file
using (var converter = new GroupDocs.Conversion.Converter("sample.emf"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMF to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**EMF to DOCX converter**](https://products.groupdocs.app/conversion/emf-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMF to DOCX"](conversion/net/images/convert-to-docx/convert-emf-to-docx.png)](https://products.groupdocs.app/conversion/emf-to-docx)