---
id: convert-vcf-to-html
url: conversion/net/convert-vcf-to-html
title: Convert VCF to HTML
description: "VCF format represents vCard File with .vcf extension. Learn how to convert VCF to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VCF to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

VCF (Virtual Card Format) or vCard is a digital file format for storing contact information. The format is widely used for data interchange among popular information exchange applications. Most operating systems such as Windows and macOS come with default applications to create and open these files. A single VCF file can contain contact information for one or multiple contacts.

## Steps to convert VCF to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VCF file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VCF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VCF file
using (var converter = new GroupDocs.Conversion.Converter("sample.vcf"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VCF to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**VCF to HTML converter**](https://products.groupdocs.app/conversion/vcf-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VCF to HTML"](conversion/net/images/convert-to-html/convert-vcf-to-html.png)](https://products.groupdocs.app/conversion/vcf-to-html)