---
id: convert-eml-to-pptx
url: conversion/net/convert-eml-to-pptx
title: Convert EML to PPTX
description: "EML format represents E-Mail Message File with .eml extension. Learn how to convert EML to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EML to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

EML file format represents email messages saved using Outlook and other relevant applications. Almost all emailing clients support this file format for its compliance with RFC-822 Internet Message Format Standard. Microsoft Outlook is default software for opening EML message types. EML files can be used for saving to disc as well as sending out to recipients using communication protocols.

## Steps to convert EML to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EML file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source EML file
using (var converter = new GroupDocs.Conversion.Converter("sample.eml"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EML to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**EML to PPTX converter**](https://products.groupdocs.app/conversion/eml-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EML to PPTX"](conversion/net/images/convert-to-pptx/convert-eml-to-pptx.png)](https://products.groupdocs.app/conversion/eml-to-pptx)