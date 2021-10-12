---
id: pptm-to-pdf
url: conversion/net/convert/pptm-to-pdf
title: Convert PPTM to PDF
description: "PPTM format represents Microsoft PowerPoint Presentation with .pptm extension. Learn how to convert PPTM to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTM to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTM extension are Macro-enabled Presentation files that are created with Microsoft PowerPoint 2007 or higher versions. They are similar to PPTX files with the difference that the lateral can't execute macros though they can contain macros. PPTM files can be edited by opening them in Microsoft PowerPoint and updating the contents. Another similar format is PPSM but it is read-only by default and starts the slideshow when opened. PPTM, like PPTX, contains slides for different presentation elements like text, images, videos, graphs and other related material.

## Steps to convert PPTM to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTM file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTM file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptm"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PPTM to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTM to PDF converter**](https://products.groupdocs.app/conversion/pptm-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTM to PDF"](conversion/net/images/convert-to-pdf/convert-pptm-to-pdf.png)](https://products.groupdocs.app/conversion/pptm-to-pdf)