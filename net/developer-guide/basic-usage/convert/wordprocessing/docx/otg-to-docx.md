---
id: otg-to-docx
url: conversion/net/convert/otg-to-docx
title: Convert OTG to DOCX
description: "OTG format represents OpenDocument Graphic Template with .otg extension. Learn how to convert OTG to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTG to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An OTG file is a drawing template that is created using the OpenDocument standard that follows the OASIS Office Applications 1.0 specification. It represents the default organization of drawing elements for a vector image that can be used to further enhance the contents of the file.

## Steps to convert OTG to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTG file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTG file
using (var converter = new GroupDocs.Conversion.Converter("sample.otg"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTG to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**OTG to DOCX converter**](https://products.groupdocs.app/conversion/otg-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTG to DOCX"](conversion/net/images/convert-to-docx/convert-otg-to-docx.png)](https://products.groupdocs.app/conversion/otg-to-docx)