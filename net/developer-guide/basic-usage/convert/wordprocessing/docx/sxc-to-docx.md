---
id: sxc-to-docx
url: conversion/net/convert/sxc-to-docx
title: Convert SXC to DOCX
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (var converter = new GroupDocs.Conversion.Converter("sample.sxc"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### SXC to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to DOCX converter**](https://products.groupdocs.app/conversion/sxc-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to DOCX"](conversion/net/images/convert-to-docx/convert-sxc-to-docx.png)](https://products.groupdocs.app/conversion/sxc-to-docx)