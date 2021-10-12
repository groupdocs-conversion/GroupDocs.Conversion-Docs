---
id: log-to-pptx
url: conversion/net/convert/log-to-pptx
title: Convert LOG to PPTX
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (var converter = new GroupDocs.Conversion.Converter("sample.log"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### LOG to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to PPTX converter**](https://products.groupdocs.app/conversion/log-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to PPTX"](conversion/net/images/convert-to-pptx/convert-log-to-pptx.png)](https://products.groupdocs.app/conversion/log-to-pptx)