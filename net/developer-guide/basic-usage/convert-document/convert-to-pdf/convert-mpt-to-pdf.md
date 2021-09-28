---
id: convert-mpt-to-pdf
url: conversion/net/convert-mpt-to-pdf
title: Convert MPT to PDF
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

To convert from Microsoft Project Template (.mpt) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MPT file
using (Converter converter = new Converter("sample.mpt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to PDF converter**](https://products.groupdocs.app/conversion/mpt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to PDF"](conversion/net/images/convert-mpt-to-pdf.png)](https://products.groupdocs.app/conversion/mpt-to-pdf)